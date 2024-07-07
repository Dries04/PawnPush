<script>
    import '.././styles.css';
    
    let sizeChesspieces = ["small", "medium", "large", "huge", "gigantic"];

    function NextSizeChesspieces() {
        
    }
</script>

<div class="Settings-Profile">
    <h1>Settings</h1>
    <hr>
    <button on:click={NextSizeChesspieces}>Size chesspieces: </button>
    Dit is de settings pagina van de PawnPush app.
</div>

<style>
    h1 {
        margin-bottom: 0;
    }

</style>