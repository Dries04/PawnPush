<script lang=ts>
    import Tile from "./Tile.svelte";

    let horizontalAxis = ["A", "B", "C", "D", "E", "F", "G", "H"];
    let verticalAxis = ['8', '7', '6', '5', '4', '3', '2', '1'];

    // Piece properties
    interface Piece {
        image: string;
        vertical: string;
        horizontal: string;
    }

    // Array of pieces in starting position
    const pieces: Piece[] = [
        { image: "bN", vertical: '8', horizontal: 'B' },
        { image: "bN", vertical: '8', horizontal: 'G' },

        { image: "bB", vertical: '8', horizontal: 'C' },
        { image: "bB", vertical: '8', horizontal: 'F' },

        { image: "bR", vertical: '8', horizontal: 'A' },
        { image: "bR", vertical: '8', horizontal: 'H' },

        { image: "bQ", vertical: '8', horizontal: 'D' },
        { image: "bK", vertical: '8', horizontal: 'E' },

        { image: "bP", vertical: '7', horizontal: 'A' },
        { image: "bP", vertical: '7', horizontal: 'B' },
        { image: "bP", vertical: '7', horizontal: 'C' },
        { image: "bP", vertical: '7', horizontal: 'D' },
        { image: "bP", vertical: '7', horizontal: 'E' },
        { image: "bP", vertical: '7', horizontal: 'F' },
        { image: "bP", vertical: '7', horizontal: 'G' },
        { image: "bP", vertical: '7', horizontal: 'H' },

        { image: "wN", vertical: '1', horizontal: 'B' },
        { image: "wN", vertical: '1', horizontal: 'G' },

        { image: "wB", vertical: '1', horizontal: 'C' },
        { image: "wB", vertical: '1', horizontal: 'F' },

        { image: "wR", vertical: '1', horizontal: 'A' },
        { image: "wR", vertical: '1', horizontal: 'H' },

        { image: "wQ", vertical: '1', horizontal: 'D' },
        { image: "wK", vertical: '1', horizontal: 'E' },

        { image: "wP", vertical: '2', horizontal: 'A' },
        { image: "wP", vertical: '2', horizontal: 'B' },
        { image: "wP", vertical: '2', horizontal: 'C' },
        { image: "wP", vertical: '2', horizontal: 'D' },
        { image: "wP", vertical: '2', horizontal: 'E' },
        { image: "wP", vertical: '2', horizontal: 'F' },
        { image: "wP", vertical: '2', horizontal: 'G' },
        { image: "wP", vertical: '2', horizontal: 'H' }
    ];

    function getImage(vertical: string, horizontal: string) {
        for (let piece of pieces) {
            if (piece.horizontal === horizontal && piece.vertical === vertical) {
                return piece.image;
            }
        }
        return "";
    }

    export let Chess_Pieces_style: string = "abstract";
    function getCorrectStyle(){
        if(Chess_Pieces_style === "abstract"){
            return "/Chess-Pieces/Kiwen-suwi/";
        }
        else if(Chess_Pieces_style === "classic"){
            return "/Chess-Pieces/caliente/";
        }
        else if(Chess_Pieces_style === "modern"){
            return "/Chess-Pieces/california/";
        }
        else if(Chess_Pieces_style === "pixel"){
            return "/Chess-Pieces/Pixel/";
        }
        else if(Chess_Pieces_style === "futuristic"){
            return "/Chess-Pieces/kosal/";
        }
        else if(Chess_Pieces_style === "weird"){
            return "/Chess-Pieces/monarchy/";
        }
        else if(Chess_Pieces_style === "funky"){
            return "/Chess-Pieces/cburnett/";
        }
    }

    export let Chess_Board_Style: string = "default";

    export let Chess_Pieces_Size: string = "large";


    // chessboard boundary (When piece is dragged outside of the chessboard, the piece will be placed in the last position of the chessboard)
    export function boundaryCheck(x: number, y: number) {

    }
    
    

    // grab the piece
    let movingPiece: HTMLElement | null = null;

    function handleMouseDown(event: MouseEvent) {
        const target = event.target as HTMLElement;
        if( target.classList.contains("tile-img")) {
            movingPiece = target;
            target.style.cursor = "grabbing";
            const x = event.clientX - 75/2;
            const y = event.clientY - 75/2;
            target.style.position = "absolute";
            target.style.left = `${x}px`;
            target.style.top = `${y}px`;
        }
    }

    // move the piece
    function handleMouseMove(event: MouseEvent) {
        const target = event.target as HTMLElement;
        if(movingPiece && target.classList.contains("tile-img")) {
            target.style.cursor = "grab";

            const x = event.clientX - 75/2;
            const y = event.clientY - 75/2;
            target.style.position = "absolute";

            target.style.left = `${x}px`;
            target.style.top = `${y}px`;
            target.style.zIndex = "1000";
        }

    }

    // drop the piece
    function handleMouseUp(event: MouseEvent) {
        const target = event.target as HTMLElement;
        if(movingPiece) {
            target.style.zIndex = "0";
            movingPiece.style.cursor = "pointer";
            movingPiece = null;
        }
    }

</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<div class="chessboard" on:mousemove={handleMouseMove} on:mousedown={handleMouseDown} on:mouseup={handleMouseUp}  >
    {#each verticalAxis as vertical}
        {#each horizontalAxis as horizontal}
            <Tile number={(horizontal.charCodeAt(0) + vertical.charCodeAt(0))} image={getImage(vertical, horizontal)} Chess_Pieces_style={getCorrectStyle()} Chess_Board_Style={Chess_Board_Style} Chess_Pieces_Size={Chess_Pieces_Size}/>
        {/each}
    {/each}
</div>

<style>
    .chessboard {
        display: grid;
        grid-template-columns: repeat(8, 1fr);
        grid-template-rows: repeat(8, 1fr);
        width: 80vh; 
        height: 80vh; 
        background-color: red;
        box-sizing: border-box;
    }
</style>

