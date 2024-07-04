<script>
	import Chessboard from './Chessboard.svelte';
	import './styles.css';

</script>

<svelte:head>
	<title>PawnPush</title>
	<meta name="description" content="PawnPush Chess Project" />
</svelte:head>

<div class="container">
	<div class="half-screen" id="left">
		<Chessboard />
	</div>
	<div class="half-screen" id="right"><h1> Dit is rechts </h1></div>
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
		margin-right: 3em;
	}

</style>
