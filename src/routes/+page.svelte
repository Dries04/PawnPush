<script>
	import Chessboard from './Components/Chessboard.svelte';
  	import Information from './Components/Information.svelte';
	import Settings from './Components/Settings.svelte';
	import Profile from './Components/Profile.svelte';
	import './styles.css';

	let infotab = "info-tab-1";

	function goToProfile() {
		infotab = "profile-tab-1";
	}
	function goToSettings() {
		infotab = "settings-tab-1";
	}
	function goToHome() {
		infotab = "info-tab-1";
	}

</script>

<svelte:head>
	<title>PawnPush</title>
	<meta name="description" content="PawnPush Chess Project" />
</svelte:head>

<div class="container">
	<div class="half-screen" id="left">
		<Chessboard />
	</div>
	<div class="half-screen" id="right">
		<div id="settings-profile" class="information-container">
			<h2 class="settings-profile">
				<button class="button-2" id="profile" on:click={goToProfile} >Profile<i id="profile-icon" class="fa-solid fa-user"></i></button>
			</h2>
			<h2 class="settings-profile">
				<button class="button-2" id="settings" on:click={goToSettings}>Settings<i id ="settings-icon" class="fa-solid fa-gear"></i></button>
			</h2>
			<h2 class="settings-profile">
				<button class="button-2" id="home" on:click={goToHome}>Home<i id ="home-icon" class="fa-solid fa-home"></i></button>
			</h2>
		</div>
		{#if infotab == "info-tab-1"}
			<Information />
		{:else if infotab == "settings-tab-1"}
			<Settings />
		{:else if infotab == "profile-tab-1"}
			<Profile />
		{/if}
	</div>
</div>

<style>
	.container {
		display: flex;
		height: 100vh;
	}

	.half-screen {
		width: 50%;
		height: 100%;
	}

	#left {
		background-color: var(--color-bg-1);
		box-sizing: border-box;
		display: grid; /* Added for centering */
		place-items: center; /* Center child elements horizontally and vertically */
	}

	#right {
		background-color: var(--color-bg-2);
		margin-right: 5%;
		margin-left: 3%;
	}


	/* settings and profile */
	.information-container {
        height: 97%;
        width: 97%;
        margin-top: 3%;
    }
	.information-container {
        height: 97%;
        width: 97%;
        margin-top: 3%;
    }
    #settings-profile {
        float: right;
        width: 50%;
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
	#home {
		margin: 0;
		padding: 0;
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
	#home-icon {
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
