<script file="ts">
	import AudioBox from '$lib/components/AudioBox.svelte';
</script>

<!-- sournd resource: https://mixkit.co/free-sound-effects/ -->
<!-- wether icons: https://github.com/basmilius/weather-icons -->
<!-- https://www.reshot.com/free-svg-icons/ -->

<div class="header"><h1 class="header__title">Focus Sounds</h1></div>

<div class="main-container">
	<AudioBox audioSrc={'light-rain.wav'} imgSrc={'rain.svg'} />

	<AudioBox audioSrc={'sunny.wav'} imgSrc={'sunny.svg'} />

	<AudioBox audioSrc={'night.wav'} imgSrc={'night.svg'} />

	<AudioBox audioSrc={'wind.wav'} imgSrc={'wind.svg'} />

	<AudioBox audioSrc={'thunderstorm.wav'} imgSrc={'thunderstorm.svg'} />

	<AudioBox audioSrc={'smoke.wav'} imgSrc={'smoke.svg'} />

	<AudioBox audioSrc={'mist.wav'} imgSrc={'mist.svg'} />

	<AudioBox audioSrc={'cafe.wav'} imgSrc={'cafe.svg'} />

	<AudioBox audioSrc={'piano.mp3'} imgSrc={'piano.svg'} />

	<AudioBox audioSrc={'meditation.mp3'} imgSrc={'meditation.svg'} />
</div>

<style>
	.header {
		padding: 1rem;
		text-align: center;
	}
	.header__title {
		color: #fff;
		font-size: 1.5rem;
		letter-spacing: 2px;
		font-weight: 300;
	}
	.main-container {
		max-width: 560px;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: center;
		margin: 0 auto;
		margin-top: 1rem;

		display: flex;
	}
</style>
