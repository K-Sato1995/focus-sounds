<script file="ts">
	let audio;
	let volumeControl;

	const changeVolume = () => {
		audio.volume = volumeControl.value / 100;
	};
	const play = () => {
		audio.play();
	};
	const pause = () => {
		audio.pause();
	};
</script>

<!-- // https://blog.shahednasser.com/how-to-style-an-audio-element/ -->

<img src="cloudy.svg" alt="My Happy SVG" class="wheather-img" />

<img src="rain.svg" alt="My Happy SVG" class="wheather-img" />

<div class="audio-player">
	<div class="controls">
		<button class="player-button" on:click={play}>Play</button>
		<button class="player-button" on:click={pause}>Pause</button>
	</div>

	<audio bind:this={audio} src="light-rain.wav" loop />

	<input
		bind:this={volumeControl}
		max="100"
		on:change={changeVolume}
		type="range"
		class="volume-control"
	/>
</div>

<style>
	.volume-control {
		-webkit-appearance: none;
		width: 100%;
		height: 3px;
		background: #d3d3d3;
		outline: none;
		opacity: 0.7;
		-webkit-transition: 0.2s;
		transition: opacity 0.2s;
	}
	.volume-control:hover {
		opacity: 1;
	}

	.volume-control::-webkit-slider-thumb {
		-webkit-appearance: none;
		appearance: none;
		width: 20px;
		height: 20px;
		border-radius: 50%;
		background: #04aa6d;
		cursor: pointer;
	}

	.wheather-img {
		width: 150px;
		height: 150px;
	}

	.audio-player {
		width: 15rem;
		height: 15rem;

		--player-button-width: 3em;
	}

	.controls {
		display: flex;
		flex-direction: row;
		align-items: center;
		width: 100%;
		margin-top: 10px;
	}

	.player-button {
		background-color: transparent;
		border: 0;
		width: var(--player-button-width);
		height: var(--player-button-width);
		cursor: pointer;
		padding: 0;
	}
</style>
