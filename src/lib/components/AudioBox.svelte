<script file="ts">
	export let audioSrc;
	export let imgSrc;

	let isPlaying = false;
	let audio;
	let volumeControl;

	const changeVolume = () => {
		audio.volume = volumeControl.value / 100;
	};

	const play = () => {
		isPlaying = true;
		audio.play();
	};

	const pause = () => {
		isPlaying = false;
		audio.pause();
	};

	const toggleAudio = () => {
		return audio.paused ? play() : pause();
	};
</script>

<div class="audio-container">
	<audio bind:this={audio} src={audioSrc} loop />
	<img src={imgSrc} alt="wheather-images" class="wheather-img" on:click={toggleAudio} />

	<input
		bind:this={volumeControl}
		max="100"
		on:change={changeVolume}
		type="range"
		class="volume-control"
		style={`display: ${isPlaying ? 'block' : 'none'}`}
	/>
</div>

<style>
	.audio-container {
		width: 150px;
		height: 150px;
		margin: 1rem;
	}

	.wheather-img {
		width: 100px;
		height: 100px;
		display: block;
		margin: 0 auto;
		opacity: 0.8;
		cursor: pointer;
	}

	.wheather-img:hover {
		opacity: 1;
	}

	.volume-control {
		-webkit-appearance: none;
		display: block;
		width: 80%;
		margin: 0 auto;
		margin-top: 1rem;
		height: 3px;
		background: #fff;
		outline: none;
		opacity: 0.7;
		cursor: pointer;
		-webkit-transition: 0.2s;
		transition: opacity 0.2s;
	}

	.volume-control:hover {
		opacity: 1;
	}

	.volume-control::-webkit-slider-thumb {
		-webkit-appearance: none;
		appearance: none;
		width: 15px;
		height: 15px;
		border-radius: 50%;
		background: #fff;
		cursor: pointer;
	}
</style>
