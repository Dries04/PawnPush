<script lang=ts>
    export let number: number = 0;
    export let image: string = "";
    export let Chess_Pieces_style: string = "/Chess-Pieces/Kiwen-suwi/";
</script>

{#if number % 2 === 0}
    {#if image === ""}
        <div class="black-tile"></div>
    {:else}
        <div class="black-tile">
            <div class="tile-img" style={`background-image: url(${Chess_Pieces_style}${image}.svg); 
                background-repeat: no-repeat; 
                background-position: center; 
                background-size: cover;`}>
            </div>
        </div>
    {/if}
{:else}
    {#if image === ""}
        <div class="white-tile"></div>
    {:else}
        <div class="white-tile">
            <div class="tile-img" style={`background-image: url(${Chess_Pieces_style}${image}.svg); 
                background-repeat: no-repeat; 
                background-position: center; 
                background-size: cover;`}>
            </div>
        </div>
    {/if}
{/if}
    
<style>
    .white-tile {
        display: grid;
        place-items: center;
        background-color: #639e61;
    }
    .black-tile {
        display: grid;
        place-items: center;
        background-color: #3f835c;
        height: 100%;
        width: 100%;
    }

    .tile-img {
        /* height: 85%;
        width: 85%; */
        height: 80px;
        width: 80px;
    }

    .tile-img:hover {
        cursor: grab;
    }

    .tile-img:active {
        cursor: grabbing;
    }

</style>