<script>
	export let context = '';
	export let description = '';
	export let backText = '';
	export let icon = '';

	let flipped = false;
	let backContent;

	function flip() {
		if (!backText) return;
		flipped = !flipped;
		if (flipped && backContent) backContent.scrollTop = 0;
	}
</script>

<div class="flip-container" class:flipped class:flippable={!!backText}>
	<div class="flipper">

		<!-- Front -->
		<div class="stat-card face front">
			<div class="stat-section">
				{#if icon}
					<div class="icon-badge">
						<img src={icon} alt="" aria-hidden="true" class="icon-img" />
					</div>
				{/if}
				{#if context}
					<div class="context-label">{context}</div>
				{/if}
				<slot />
			</div>
			{#if description}
				<div class="desc-section">
					<p class="desc-text">{description}</p>
				</div>
			{/if}
			{#if backText}
				<button class="flip-hint" on:click={flip}>Read more about this finding →</button>
			{/if}
		</div>

		<!-- Back -->
		{#if backText}
			<div class="stat-card face back">
				<div class="back-content back-text" bind:this={backContent}>
					{#if icon}<div class="back-icon-badge"></div>{/if}
					{#if context}<div class="back-title">{context}</div>{/if}
					{@html backText}
				</div>
				<button class="flip-hint" on:click={flip}>← Click to go back</button>
			</div>
		{/if}

	</div>
</div>

<style>
	.flip-container {
		max-width: 680px;
		width: 680px;
		margin-top: 32px;
		margin-bottom: 32px;
		perspective: 1200px;
		touch-action: pan-y;
	}

	.flipper {
		position: relative;
		width: 100%;
		transform-style: preserve-3d;
		transition: transform 0.55s cubic-bezier(0.4, 0, 0.2, 1);
	}

	.flip-container.flipped .flipper {
		transform: rotateY(180deg);
	}

	.face {
		backface-visibility: hidden;
		-webkit-backface-visibility: hidden;
	}

	.back {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		transform: rotateY(180deg);
	}

	.stat-card {
		width: 100%;
		background-color: var(--mjBlue);
		border-radius: 0px;
		overflow: hidden;
		box-sizing: border-box;
	}


	.back {
		display: flex;
		flex-direction: column;
	}

	.back-content {
		padding: 48px 48px 24px;
		overflow-y: auto;
		flex: 1;
		box-sizing: border-box;
	}

	.back-text {
		font-family: RobotoRegular, sans-serif;
		font-size: 16px;
		line-height: 1.5;
		color: var(--mjWhite);
	}

	.back-text :global(p) {
		margin: 0 0 1em;
		color: var(--mjWhite);
		font-size: inherit;
		line-height: inherit;
	}

	.back-text :global(p:last-child) {
		margin-bottom: 0;
	}

	.back-text :global(a) {
		color: var(--mjYellow);
		text-underline-offset: 3px;
	}

	.back-title {
		font-family: RobotoBold, sans-serif;
		font-size: 22px;
		color: var(--mjWhite);
		padding-bottom: 10px;
		margin-bottom: 18px;
		border-bottom: solid 2px rgba(255, 255, 255, 1);
		line-height: 1.2;
	}

	.back-text :global(strong) {
		font-family: RobotoBold, sans-serif;
		color: var(--mjWhite);
	}

	.flip-hint {
		display: block;
		width: 100%;
		background: rgba(255, 255, 255, 0.1);
		border: none;
		border-top: 1px solid rgba(255, 255, 255, 0.2);
		font-family: RobotoBold, sans-serif;
		font-size: 14px;
		color: rgba(255, 255, 255, 0.95);
		padding: 14px 48px;
		text-align: right;
		cursor: pointer;
		letter-spacing: 0.03em;
		transition: background 0.15s, color 0.15s;
	}

	.flip-hint:hover {
		background: rgba(255, 255, 255, 0.18);
		color: var(--mjWhite);
	}

	.stat-section {
		padding: 48px 48px 40px;
		min-height: 360px;
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		gap: 22px;
		border-top: solid 1px var(--mjBlue);
	}

	.back-icon-badge {
		width: 42px;
		height: 42px;
		background-color: var(--mjBackgroundGrey);
		opacity: 0.25;
		float: right;
		margin-top: -48px;
		margin-left: -48px;
	}

	.icon-badge {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 42px;
		height: 42px;
		background-color: var(--mjBackgroundGrey);
		border-radius: 0%;
		flex-shrink: 0;
		margin-top: -48px;
	}

	.icon-img {
		width: 26px;
		height: 26px;
		/* converts black SVG paths to #0D0A45 (mjBlue) */
		filter: brightness(0) saturate(100%) invert(7%) sepia(63%) saturate(1800%) hue-rotate(228deg) brightness(70%) contrast(110%);
	}

	.context-label {
		font-family: RobotoBold, sans-serif;
		font-size: 31px;
		color: var(--mjWhite);
		text-align: left;
		margin-top: -10px;
		padding-bottom: 10px;
		margin-bottom: 15px;
		border-bottom: solid 2px rgba(255, 255, 255, 1);
	}

	.desc-section {
		padding: 24px 48px 32px;
		border-top: 1px solid rgba(255, 255, 255, 0.33);
	}

	.desc-text {
		font-family: RobotoRegular, sans-serif;
		font-size: 12px;
		line-height: 19px;
		color: var(--mjPaleGrey);
		margin: 0;
		padding: 0;
		opacity: 0.8;
	}

	@media (max-width: 550px) {
		.flip-container {
			width: 100%;
			max-width: 100%;
		}

		.stat-card {
			width: 100%;
			max-width: 100%;
		}

		.stat-section {
			padding: 32px 32px 28px;
			gap: 16px;
		}

		.icon-badge {
			margin-top: -32px;
		}

		.back-icon-badge {
			margin-top: -32px;
		}

		.back-title {
			margin-top: 15px;
		}

		.context-label {
			font-size: 25px;
			margin-top: -8px;
			padding-bottom: 8px;
			margin-bottom: 10px;
		}

		.desc-section {
			padding: 18px 32px 24px;
		}

		.desc-text {
			font-size: 11px;
			line-height: 17px;
		}

		.back-content {
			padding: 32px 32px 20px;
		}

		.back-text {
			font-size: 16px;
			line-height: 1.45;
		}


		.flip-hint {
			padding: 12px 32px 16px;
		}
	}
</style>
