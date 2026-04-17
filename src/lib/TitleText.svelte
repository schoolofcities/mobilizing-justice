<script>
	export let title = '';
	export let subtitle = '';
	export let description = '';
</script>

<div class="title-block">
	{#if subtitle}
		<div class="subtitle">{subtitle}</div>
	{/if}
	<h1 class="title">{title}</h1>
	{#if description}
	<p class="description">
		{description}
	</p>
	{/if}
</div>

<style>
	.title-block {
		max-width: 720px;
		margin: auto;
		padding: 0 20px;
		border-left: 12px solid var(--mjYellow);
		padding-left: 24px;
		margin-bottom: 80px;
		margin-top: 80px;
	}

	.subtitle {
		font-family: RobotoRegular, sans-serif;
		font-size: 20px;
		color: var(--mjPurple);
		margin-bottom: 10px;
	}

	.title {
		font-family: RobotoBold, sans-serif;
		font-size: 62px;
		color: var(--mjBlue);
		margin: 0;
		padding: 0;
	}
	
	.description {
		font-family: RobotoRegular, sans-serif;
		font-size: 24px;
		color: var(--mjBlue);
	}

</style>
