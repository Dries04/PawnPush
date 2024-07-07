<script>
  import { writable } from 'svelte/store';
    import '.././styles.css';
    
    export let ChessPiecesSize = "large";
    let sizeChesspieces = ["small", "medium", "large", "huge", "gigantic"];

    

    function NextSizeChesspieces() {
        let index = sizeChesspieces.indexOf(ChessPiecesSize);
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
    <button class="button-1" on:click={NextSizeChesspieces}>Size chesspieces: {ChessPiecesSize}</button>
    <button class="button-1">test button</button>
    <button class="button-1">test button nog eens</button>
    <button class="button-1">Wat is me dit</button>
    <p>Dit is de settings pagina van de PawnPush app.</p>
</div>

<style>
    h1 {
        margin-left: 5%;
    }

</style>