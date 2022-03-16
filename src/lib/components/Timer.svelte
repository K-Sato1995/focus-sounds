<script>
	let defaultTime = 1500;
	let timer = 1500;
	let isRunning = false;
	let intervaleID;

	const formatTime = (seconds) => {
		const h = Math.floor(seconds / 3600);
		const m = Math.floor((seconds % 3600) / 60);
		const s = Math.round(seconds % 60);
		return [h, m > 9 ? m : h ? '0' + m : m || '0', s > 9 ? s : '0' + s].filter(Boolean).join(':');
	};

	const start = () => {
		isRunning = true;
		intervaleID = setInterval(function () {
			if (timer > 0) {
				timer--;
			} else {
				alert("Time's up");
				pause();
				timer = 0;
			}
		}, 1000);
	};

	const reset = () => {
		isRunning = false;
		timer = defaultTime;
		clearInterval(intervaleID);
	};

	const pause = () => {
		isRunning = false;
		clearInterval(intervaleID);
	};
</script>

<div class="timer">
	<h2 class="timer__remaining-time">
		{formatTime(timer)}
		<div class="timer__add-minus-buttuns">
			<button
				class="timer__add-minus-buttuns__button"
				on:click={() => {
					timer += 60;
				}}>+</button
			>
			<button
				class="timer__add-minus-buttuns__button"
				on:click={() => {
					if (timer >= 60) {
						timer -= 60;
					}
				}}>-</button
			>
		</div>
	</h2>

	<div class="timer__buttuns-play-pause">
		{#if isRunning}
			<i class="gg-play-pause-o" on:click={pause} />
			{#if defaultTime !== timer}<i class="gg-undo" on:click={reset} />{/if}
		{:else if timer === 0}
			<i class="gg-undo" on:click={reset} />
		{:else}
			<i class="gg-play-button-o" on:click={start} />

			{#if defaultTime !== timer}<i class="gg-undo" on:click={reset} />{/if}
		{/if}
	</div>
</div>

<style>
	.timer {
		display: flex;
		/* border: solid 1px #fff; */
	}

	.timer__remaining-time {
		color: #fff;
		font-size: 1.5rem;
		letter-spacing: 5px;
		/* border: solid 1px #fff; */
	}

	.timer__buttuns-play-pause {
		/* border: solid 1px #fff; */
		margin-left: 0.4rem;
		display: flex;
		flex-direction: column;
		justify-content: center;
		justify-content: space-evenly;
		padding: 0.5rem;
	}

	.timer__add-minus-buttuns {
		/* border: solid 1px red; */
		display: flex;
		flex-direction: row;
		justify-content: center;
		padding: 0.2rem;
	}

	.timer__add-minus-buttuns__button {
		color: #fff;
		border: none;
		background: none;
		cursor: pointer;
		background-color: none;
		padding: 0 0.7rem;
	}

	/* ICON DESIGN */
	.gg-play-button-o {
		cursor: pointer;
		box-sizing: border-box;
		position: relative;
		display: block;
		transform: scale(var(--ggs, 1));
		width: 22px;
		height: 22px;
		border: 2px solid;
		border-radius: 20px;
		color: #fff;
	}
	.gg-play-button-o::before {
		content: '';
		display: block;
		box-sizing: border-box;
		position: absolute;
		width: 0;
		height: 10px;
		border-top: 5px solid transparent;
		border-bottom: 5px solid transparent;
		border-left: 6px solid;
		top: 4px;
		left: 7px;
	}

	.gg-play-pause-o {
		cursor: pointer;
		box-sizing: border-box;
		position: relative;
		display: block;
		transform: scale(var(--ggs, 1));
		width: 22px;
		height: 22px;
		border: 2px solid;
		border-radius: 22px;
		color: #fff;
	}
	.gg-play-pause-o::before {
		content: '';
		display: block;
		box-sizing: border-box;
		position: absolute;
		width: 6px;
		height: 6px;
		left: 6px;
		top: 6px;
		border-left: 2px solid;
		border-right: 2px solid;
	}

	.gg-undo {
		margin-left: 0.2rem;
		box-sizing: border-box;
		cursor: pointer;
		position: relative;
		display: block;
		color: #fff;
		transform: scale(var(--ggs, 1));
		width: 14px;
		height: 14px;
		border: 2px solid;
		border-left-color: transparent;
		border-radius: 100px;
	}
	.gg-undo::before {
		content: '';
		display: block;
		box-sizing: border-box;
		position: absolute;
		width: 6px;
		height: 6px;
		border-top: 2px solid;
		border-left: 2px solid;
		top: -3px;
		left: -1px;
		transform: rotate(-68deg);
	}
</style>
