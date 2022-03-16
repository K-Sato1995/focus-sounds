<script file="ts">
	export let audioSrc;
	export let imgSrc;

	let audio;
	let volumeControl;

	const changeVolume = () => {
		audio.volume = volumeControl.value / 100;
	};

	const toggleAudio = () => {
		return audio.paused ? audio.play() : audio.pause();
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
	/>
</div>

<style>
	.audio-container {
		border: solid 1px;
		width: 150px;
		height: 200px;
	}

	.wheather-img {
		width: 150px;
		height: 150px;
		opacity: 0.8;
		cursor: pointer;
	}

	.wheather-img:hover {
		opacity: 1;
	}

	.volume-control {
		-webkit-appearance: none;
		width: 100%;
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
