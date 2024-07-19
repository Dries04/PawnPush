<script lang="ts">
	import Information from './Components/Information.svelte';
	import './styles.css';
	import { Chess } from 'svelte-chess';

	let ChessPiecesSize: string;
	let ChessPiecesStyle: string;
	let ChessBoardStyle: string;

	function handleMessage(event: { detail: { message: { ChessPiecesSize: string; ChessPiecesStyle: string; ChessBoardStyle: string; }; }; }) {
		if(event.detail.message.ChessPiecesSize){
			ChessPiecesSize = event.detail.message.ChessPiecesSize;
		}
		if(event.detail.message.ChessPiecesStyle){
			ChessPiecesStyle = event.detail.message.ChessPiecesStyle;
		}
		if(event.detail.message.ChessBoardStyle){
			ChessBoardStyle = event.detail.message.ChessBoardStyle;
		}
	}

</script>

<svelte:head>
	<title>PawnPush</title>
	<meta name="description" content="PawnPush Chess Project" />
</svelte:head>

<div class="container">
	<div class="half-screen" id="left">
		<div class="testtest">
			<link rel="stylesheet" href="/chess-styles/chess-style.css" />
			<Chess class="cg-paper"/>
		</div>
	</div>
	<div class="half-screen" id="right">
		<Information on:message={handleMessage}/>
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

	.testtest {
		width: 90%;
		height: 90%;
		margin-top: 6%;
		margin-left: 6%;
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

</style>
