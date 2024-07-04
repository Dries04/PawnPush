<script lang=ts>
    export let number: number = 0;
    export let image: string = "";
</script>

{#if number % 2 === 0}
    {#if image === ""}
        <div class="black-tile"></div>
    {:else}
        <div class="black-tile">
            <img src="/Chess-Pieces/Kiwen-suwi/{image}.svg"  alt=""/>
        </div>
    {/if}
{:else}
    {#if image === ""}
        <div class="white-tile"></div>
    {:else}
        <div class="white-tile">
            <img src="/Chess-Pieces/Kiwen-suwi/{image}.svg"  alt=""/>
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