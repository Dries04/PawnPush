<script>
    import './styles.css';

    function goToProfile() {
        var infoTabs = document.querySelectorAll('.info-tab');
  
        // Hide all content divs
        for (var i = 0; i < infoTabs.length; i++) {
            infoTabs[i].classList.remove('active');
        }
        
        // Show the selected content div
        //infoTabs[1].style.visibility = 'visible'; // Make sure it's visible before adding 'active'
        infoTabs[0].classList.add('active');
    }

    function goToSettings() {
        var infoTabs = document.querySelectorAll('.info-tab');
  
        // Hide all content divs
        for (var i = 0; i < infoTabs.length; i++) {
            infoTabs[i].classList.remove('active');
        }
        
        // Show the selected content div
        //infoTabs[1].style.visibility = 'visible'; // Make sure it's visible before adding 'active'
        infoTabs[1].classList.add('active');
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
    <div class="info-tab active">
        <h2>INFO tab 1</h2>
        <p>Hello dit is een test</p>
    </div>
    <div class="info-tab">
        <h2>INFO tab 2</h2>
        <p>Heykes dit is de tweede tab</p>
    </div>
    <div class="info-tab">
        <h2>INFO tab 3</h2>
        <p>hoihoi dit is het derde tab</p>
    </div>
</div>

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

    /* Info tabs */

    .info-tab {
        opacity: 0;
        visibility: hidden;
        transition: opacity 0.5s ease, visibility 0.5s ease;
    }

    .info-tab.active {
        opacity: 1;
        visibility: visible;
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