<script lang="ts">
	import Information from './Components/Information.svelte';
	import './styles.css';
	import { Chess } from 'svelte-chess';

	let ChessBoardSize: string;
	let ChessPiecesStyle: string = "abstract";
	let ChessBoardStyle: string = "default";

	function handleMessage(event: { detail: { message: { ChessBoardSize: string; ChessPiecesStyle: string; ChessBoardStyle: string; }; }; }) {
		if(event.detail.message.ChessBoardSize){
			ChessBoardSize = event.detail.message.ChessBoardSize;
			switchChessBoardSize();
		}
		if(event.detail.message.ChessPiecesStyle){
			ChessPiecesStyle = event.detail.message.ChessPiecesStyle;
		}
		if(event.detail.message.ChessBoardStyle){
			ChessBoardStyle = event.detail.message.ChessBoardStyle;
		}
	}

	let chessboardWidth = 80;
	let chessboardtop = 6;

	function switchChessBoardSize(){
		if(ChessBoardSize === "small"){
			chessboardWidth = 40;
			chessboardtop = 6;
		}
		else if(ChessBoardSize === "medium"){
			chessboardWidth = 65;
			chessboardtop = 6;
		}
		else if(ChessBoardSize === "large"){
			chessboardWidth = 80;
			chessboardtop = 6;

		}
		else if(ChessBoardSize === "huge"){
			chessboardWidth = 90;
			chessboardtop = 6;
		}
	}

	$: style_chessboardSize = `width: ${chessboardWidth}%; height: ${chessboardWidth}%; margin-top: ${chessboardtop}%; margin-left: ${chessboardtop}%;`;

	// Chessboard api
	let history: any, turn: any, moveNumber, chess: Chess;

</script>

<svelte:head>
	<title>PawnPush</title>
	<meta name="description" content="PawnPush Chess Project" />
</svelte:head>

<div class="container">
	<div class="half-screen" id="left">
		{#key ChessBoardSize}
			<div style={style_chessboardSize}> 
				{#key ChessPiecesStyle}
					{#key ChessBoardStyle}
						{#if ChessPiecesStyle === "abstract" && ChessBoardStyle === "default"}
							<link rel="stylesheet" href="/chess-styles/Kiwen-suwi_default.css" />
						{:else if ChessPiecesStyle === "modern" && ChessBoardStyle === "default"}
							<link rel="stylesheet" href="/chess-styles/caliente_default.css" />
						{:else if ChessPiecesStyle === "pixel" && ChessBoardStyle === "default"}
							<link rel="stylesheet" href="/chess-styles/Pixel_default.css" />
						{/if}
							<Chess class="cg-paper" bind:this={chess} bind:turn={turn} bind:history={history}/>
							<div class="space"></div>
							<button class="button-2" id="board_nav" on:click={()=>chess?.reset()}>Reset</button>
							<button class="button-2" id="board_nav" on:click={()=>chess?.undo()}>Undo</button>
							<div></div>
					{/key}
				{/key}				
			</div>
		{/key}
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
	.space {
		height: 10px;
	}
	#board_nav {
		margin: 0;
		padding: 0.5em;
		border: 0;
		font-size: 0.9em;
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
