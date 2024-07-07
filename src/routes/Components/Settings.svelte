<script>
    import '.././styles.css';
    
    export let ChessPiecesSize = "large";
    let sizeChesspieces = ["small", "medium", "large", "huge", "gigantic"];

    function NextSizeChesspieces() {
        let index = sizeChesspieces.findIndex((value) => value === ChessPiecesSize);
        index++;
        if (index >= sizeChesspieces.length) {
            index = 0;
        }
        ChessPiecesSize = sizeChesspieces[index];
    }

</script>

<div class="Settings-Profile">
    <h1>Settings</h1>
    <hr>
    <button on:click={NextSizeChesspieces}>Size chesspieces: {ChessPiecesSize}</button>
    Dit is de settings pagina van de PawnPush app.
</div>

<style>
    h1 {
        margin-bottom: 0;
    }

</style>