<script lang=ts>
    export let number: number = 0;
    export let image: string = "";
    export let Chess_Pieces_style: string = "/Chess-Pieces/Kiwen-suwi/";
    export let Chess_Board_Style: string = "default";
    export let Chess_Pieces_Size: string = "large";

</script>

{#if number % 2 === 0}
    {#if image === ""}
        <div class="black-tile{Chess_Board_Style}"></div>
    {:else}
        <div class="black-tile{Chess_Board_Style}">
            <div class="tile-img{Chess_Pieces_Size}" style={`background-image: url(${Chess_Pieces_style}${image}.svg);
                background-repeat: no-repeat;
                background-position: center;
                background-size: cover;`}>
            </div>
        </div>
    {/if}
{:else}
    {#if image === ""}
        <div class="white-tile{Chess_Board_Style}"></div>
    {:else}
        <div class="white-tile{Chess_Board_Style}">
            <div class="tile-img{Chess_Pieces_Size}" style={`background-image: url(${Chess_Pieces_style}${image}.svg);
                background-repeat: no-repeat;
                background-position: center;
                background-size: cover;`}>
            </div>
        </div>
    {/if}
{/if}

<style>
    /* Chessboard styles */
    /* DEFAULT */
    .white-tiledefault{
        display: grid;
        place-items: center;
        background-color: #639e61;
    }
    .black-tiledefault{
        display: grid;
        place-items: center;
        background-color: #3f835c;
        height: 100%;
        width: 100%;
    }
    /* CLASSIC */
    .white-tileclassic{
        display: grid;
        place-items: center;
        background-color: #f0d9b5;
    }
    .black-tileclassic{
        display: grid;
        place-items: center;
        background-color: #b58863;
        height: 100%;
        width: 100%;
    }
    /* MODERN */
    .white-tilemodern{
        display: grid;
        place-items: center;
        background-color: rgb(255, 255, 255);
    }
    .black-tilemodern{
        display: grid;
        place-items: center;
        background-color: rgb(90, 90, 90);
        height: 100%;
        width: 100%;
    }
    /* CHESS.COM */
    .white-tilechesscom{
        display: grid;
        place-items: center;
        background-color: #eeeed3;
    }
    .black-tilechesscom{
        display: grid;
        place-items: center;
        background-color: #759556;
        height: 100%;
        width: 100%;
    }

    /* Chess Piece Size */
    /* small */
    .tile-imgsmall {
        /* height: 50%;
        width: 50%; */
        height: 35px;
        width: 35px;
    }
    /* medium */
    .tile-imgmedium {
        /* height: 65%;
        width: 65%; */
        height: 55px;
        width: 55px;
    }
    /* large */
    .tile-imglarge {
        /* height: 85%;
        width: 85%; */
        height: 75px;
        width: 75px;
    }
    /* extra-large */
    .tile-imghuge {
        /* height: 100%;
        width: 100%; */
        height: 95px;
        width: 95px;
    }
    /* gigantic */
    .tile-imggigantic {
        /* height: 120%;
        width: 120%; */
        height: 115px;
        width: 115px;
    }

    /* .tile-img {
        height: 85%;
        width: 85%;
        height: 70px;
        width: 70px;
    } */

    .tile-img:hover {
        cursor: pointer;
    }

    .tile-img:active {
        cursor: grab;
    }

</style>