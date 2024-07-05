<script>
    import './styles.css';

    function goToProfile() {
        console.log("Profile");
    }
    function goToSettings() {

    }

</script>

<div class="information-container">
    <div id="settings-profile">
        <h2 class="settings-profile">
            <button class="button-2" id="profile" on:click={goToProfile} >Profile<i id="profile-icon" class="fa-solid fa-user"></i></button>
        </h2>
        <h2 class="settings-profile">
            <button class="button-2" id="settings" on:click={goToSettings}>Settings<i id ="settings-icon" class="fa-solid fa-gear"></i></button>
        </h2>
    </div>
</div>
<div></div>

<style>
    .information-container {
        height: 97%;
        width: 97%;
        margin-top: 3%;
    }
    #settings-profile {
        float: right;
        width: 30%;
        height: 10%;
    }
    .settings-profile {
        margin: 0;
        padding: 0;
        border: 0;
        float: right;
    }

    /* button-styling */
    #settings {
        margin: 0;
        padding: 0;
        border: 0;
        float: right;
    }
    #profile {
        margin: 0;
        padding: 0;
        padding-right: 1em;
        border: 0;
        float: right;
    }
    #settings-icon {
        margin: 0;
        padding-left: 0.5em;
        padding-right: 1em;
        border: 0;
        float: right;
    }
    #profile-icon {
        margin: 0;
        padding-left: 0.5em;
        padding-right: 1em;
        border: 0;
        float: right;
    }
    .button-2 {
        background-color: var(--color-bg-2);
        font-family: var(--font-family-1);
        font-size: 0.6em;
        color: var(--color-text-1);
        border: 0;
        border-radius: 0.5em;
        padding: 0.5em;
        margin: 0.5em;
        cursor: pointer;
    }
    .button-2:hover {
        color: var(--color-text-2);
        transition: 0.4s;
    }


</style>