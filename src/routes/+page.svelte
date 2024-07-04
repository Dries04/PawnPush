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
		<h1> Dit is links</h1>
		<Chessboard />
	</div>
	<div class="half-screen" id="right"><h1> Dit is rechts </h1></div>
</div>

<style>
	.container {
		display: flex;
	}

	.half-screen {
		width: 50%;
		height: 100%;
		display: border-box;
	}

	#left {
		background-color: var(--color-bg-1);
		margin-left: 1em;
	}

	#right {
		background-color: var(--color-bg-2);
		margin-right: 1em;
	}

</style>
