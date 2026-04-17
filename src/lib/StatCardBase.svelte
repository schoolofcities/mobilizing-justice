<script>
	export let context = '';
	export let description = '';
</script>

<div class="stat-card">
	<div class="stat-section">
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
</div>

<style>
	.stat-card {
		max-width: 680px;
		width: 680px;
		margin-left: 0px;
		background-color: var(--mjBlue);
		border-radius: 0px;
		overflow: hidden;
		box-sizing: border-box;
		margin-top: 32px;
		margin-bottom: 32px;
	}

	.stat-section {
		padding: 48px 48px 40px;
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		gap: 22px;
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
</style>
