<script>
    import '.././styles.css';

    let WhiteRepertoireName = "Name your repertoire";

    function goToNextPageInRepertoire(){
        
    }
</script>

<div class="Rep">
    <div class="sub-heading" >Board Style Settings</div>
    <hr>
    <button class="button-1" on:click={goToNextPageInRepertoire}><div id="size-left">White repertoire</div> <div id="size-right">{WhiteRepertoireName}</div></button>
</div>

<style>
    #size-left {
        float: left;
        margin-left: 10%;
        padding: 0px;
    }
    #size-right {
        float: right;
        margin-right: 10%;
    }
</style>