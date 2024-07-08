<script>
    import '.././styles.css';

    function goToProfile(){
        const profileDiv = document.querySelector('.Profile-div');
        const settingsDiv = document.querySelector('.Settings-div');
        const infoDiv = document.querySelector('.Info-div');

        // @ts-ignore
        profileDiv.style.visibility = "visible";
        // @ts-ignore
        settingsDiv.style.visibility = "hidden";
        // @ts-ignore
        infoDiv.style.visibility = "hidden";
    }
    function goToSettings(){
        const profileDiv = document.querySelector('.Profile-div');
        const settingsDiv = document.querySelector('.Settings-div');
        const infoDiv = document.querySelector('.Info-div');

        // @ts-ignore
        profileDiv.style.visibility = "hidden";
        // @ts-ignore
        settingsDiv.style.visibility = "visible";
        // @ts-ignore
        infoDiv.style.visibility = "hidden";
    }
    function goToHome(){
        const profileDiv = document.querySelector('.Profile-div');
        const settingsDiv = document.querySelector('.Settings-div');
        const infoDiv = document.querySelector('.Info-div');

        // @ts-ignore
        profileDiv.style.visibility = "hidden";
        // @ts-ignore
        settingsDiv.style.visibility = "hidden";
        // @ts-ignore
        infoDiv.style.visibility = "visible";
    }

    // Settings
    // Chesspieces size
    let ChessPiecesSize = "large";
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

<!-- NAVIGATION on top right -->
<div>
    <h2>
        <button class="button-2" id="profile" on:click={goToProfile} >Profile<i id="profile-icon" class="fa-solid fa-user"></i></button>
    </h2>
    <h2>
        <button class="button-2" id="settings" on:click={goToSettings}>Settings<i id ="settings-icon" class="fa-solid fa-gear"></i></button>
    </h2>
    <h2>
        <button class="button-2" id="home" on:click={goToHome}>Home<i id ="home-icon" class="fa-solid fa-home"></i></button>
    </h2>
</div>

<div class="Main-div">
    <!-- INFO DIV -->
    <div class="Info-div">
        <h1>Repertoire Builder</h1>
    </div>

    <!-- SETTINGS DIV -->
    <div class="Settings-div">
        <h1>Settings</h1>
        <hr>
        <button class="button-1" on:click={NextSizeChesspieces}>Size chesspieces: {ChessPiecesSize}</button>
        <button class="button-1">test button</button>
        <button class="button-1">test button nog eens</button>
        <button class="button-1">Wat is me dit</button>
    </div>

    <!-- PROFILE DIV -->
    <div class="Profile-div">
        <h1>Profile</h1>
        placeholder for profile, placeholder for profile
    </div>
</div>


<style>
    /* big divs */
    .Main-div {
        margin-top: 10%;
        position: relative;
    }
    .Info-div {
        width: 100%;
        height: 100%;
        position: absolute;
        z-index: 1;
        visibility: visible;
    }
    .Settings-div {
        width: 100%;
        height: 100%;
        position: absolute;
        z-index: 2;
        visibility: hidden;
    }
    .Profile-div {
        width: 100%;
        height: 100%;
        position: absolute;
        z-index: 3;
        visibility: hidden;
    }

    /* standard html */
    h1{
        margin-left: 10%;
    }

</style>