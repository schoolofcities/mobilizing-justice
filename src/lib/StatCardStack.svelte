<script>
	import StatCardBase from './StatCardBase.svelte';

	export let context = '';
	export let description = '';
	export let backText = '';
	export let sharedLabel = '';
	export let icon = '';

	// stats: [{ stat, label, color }]
	export let stats = [];

	// Legacy two-item props from StatCardComparison
	export let stat1 = null;
	export let label1 = '';
	export let color1 = 'var(--mjYellow)';
	export let stat2 = null;
	export let label2 = '';
	export let color2 = 'var(--mjGreen)';

	$: items = stats.length
		? stats
		: stat1 !== null
			? [{ stat: stat1, label: label1, color: color1 }, { stat: stat2, label: label2, color: color2 }]
			: [];
</script>

<StatCardBase {context} {description} {backText} {icon}>
	<div class="stack">
		{#if sharedLabel}
			<p class="shared-label">{sharedLabel}</p>
		{/if}
		<div class="numbers-row">
			{#each items as item}
				<div class="stat-block">
					<div class="number" style="color: {item.color}">{item.stat}</div>
					<div class="group-label">{item.label}</div>
				</div>
			{/each}
		</div>
	</div>
</StatCardBase>

<style>
	.stack {
		display: flex;
		flex-direction: column;
		gap: 20px;
		width: 100%;
	}

	.shared-label {
		font-family: RobotoRegular, sans-serif;
		font-size: 18px;
		color: var(--mjWhite);
		margin: 0;
		line-height: 1.4;
	}

	.numbers-row {
		display: flex;
		flex-wrap: wrap;
		align-items: flex-start;
		gap: 24px;
		width: 100%;
	}

	.stat-block {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		gap: 6px;
		flex: 1;
	}

	.number {
		font-family: RobotoBold, sans-serif;
		font-size: 72px;
		line-height: 1;
		letter-spacing: -1px;
	}

	.group-label {
		font-family: RobotoBold, sans-serif;
		font-size: 15px;
		color: var(--mjWhite);
		letter-spacing: 0.03em;
	}

	@media (max-width: 550px) {
		.number {
			font-size: 52px;
		}

		.shared-label {
			font-size: 15px;
		}

		.numbers-row {
			gap: 16px;
		}
	}
</style>
