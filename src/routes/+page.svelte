<script lang="ts">
	import Information from './Components/Information.svelte';
	import './styles.css';
	import { Chess } from 'svelte-chess';

	let ChessBoardSize: string;
	let ChessPiecesStyle: string;
	let ChessBoardStyle: string;

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

	let chessboardWidth = 90;
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
			chessboardWidth = 90;
			chessboardtop = 6;
		}
	}

	$: style_chessboardSize = `width: ${chessboardWidth}%; height: ${chessboardWidth}%; margin-top: ${chessboardtop}%; margin-left: ${chessboardtop}%;`;

</script>

<svelte:head>
	<title>PawnPush</title>
	<meta name="description" content="PawnPush Chess Project" />
</svelte:head>

<div class="container">
	<div class="half-screen" id="left">
		{#key ChessBoardSize}
			<div class="Chessboard_container" style={style_chessboardSize}> 
				<link rel="stylesheet" href="/chess-styles/chess-style.css" />
				{#key ChessPiecesStyle}
					<Chess class="cg-paper" />
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

	/* .Chessboard_container {
		width: 90%;
		height: 90%;
		margin-top: 6%;
		margin-left: 6%;
	} */

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
