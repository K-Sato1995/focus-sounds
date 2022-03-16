<script file="ts">
	import AudioBox from '$lib/components/AudioBox.svelte';
</script>

<!-- sournd resource: https://mixkit.co/free-sound-effects/ -->
<!-- wether icons: https://github.com/basmilius/weather-icons -->
<!-- https://www.reshot.com/free-svg-icons/ -->
<!-- fill="[^"]*" -->

<div class="main-container">
	<AudioBox audioSrc={'light-rain.wav'} imgSrc={'rain.svg'} />

	<AudioBox audioSrc={'sunny.wav'} imgSrc={'sunny.svg'} />

	<AudioBox audioSrc={'night.wav'} imgSrc={'night.svg'} />

	<AudioBox audioSrc={'wind.wav'} imgSrc={'wind.svg'} />

	<AudioBox audioSrc={'thunderstorm.wav'} imgSrc={'thunderstorm.svg'} />

	<AudioBox audioSrc={'smoke.wav'} imgSrc={'smoke.svg'} />

	<AudioBox audioSrc={'mist.wav'} imgSrc={'mist.svg'} />

	<AudioBox audioSrc={'cafe.wav'} imgSrc={'cafe.svg'} />

	<AudioBox audioSrc={'cafe.wav'} imgSrc={'cafe.svg'} />

	<AudioBox audioSrc={'piano.mp3'} imgSrc={'piano.svg'} />
	<AudioBox audioSrc={'meditation.mp3'} imgSrc={'meditation.svg'} />
</div>

<style>
	.main-container {
		max-width: 860px;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: space-between;
		border: solid 1px #fff;
		margin: 0 auto;
		display: flex;
	}
</style>
