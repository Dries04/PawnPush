<script>
    let horizontalAxis = ["A", "B", "C", "D", "E", "F", "G", "H"];
    let verticalAxis = ['8', '7', '6', '5', '4', '3', '2', '1'];
</script>

<div class="chessboard">
    {#each verticalAxis as vertical}
        {#each horizontalAxis as horizontal}
            {#if (horizontal.charCodeAt(0) + vertical.charCodeAt(0)) % 2 === 0}
                <div class="black-tile">
                    <img src="/Chess-Pieces/Kiwen-suwi/bP.svg" alt=""/>
                </div>
            {:else}
                <div class="white-tile">
                </div>
            {/if}
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
    .white-tile {
        display: grid;
        place-items: center;
        background-color: #639e61;
    }
    .black-tile {
        display: grid;
        place-items: center;
        background-color: #3f835c;
    }

    .black-tile img {
        width: 80%;
        height: 80%;
    }

    .white-tile img {
        width: 80%;
        height: 80%;
    }
</style>