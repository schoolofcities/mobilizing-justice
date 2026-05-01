<script>
	import StatCardBase from './StatCardBase.svelte';

	export let context = '';
	export let description = '';
	// groups: [{ label?: string, bars: [{ label: string, value: number, color?: string }] }]
	export let groups = [];
	// fallback colors applied in bar order when bar.color is not set
	export let colors = ['var(--mjYellow)', 'var(--mjGreen)', 'var(--mjPurple)', 'var(--mjBlue)'];
</script>

<StatCardBase {context} {description}>
	<div class="bar-chart">
		{#each groups as group, i}
			{#if i > 0}<div class="row-divider"></div>{/if}
			{#if group.label}<div class="metric-label">{group.label}</div>{/if}
			{#each group.bars as bar, j}
				{@const barColor = bar.color ?? colors[j % colors.length]}
				<span class="bar-label">{bar.label}</span>
				<div class="bar-track">
					<div class="bar" style="flex-basis: {bar.value}%; background-color: {barColor}"></div>
					<span class="pct" style="color: {barColor}">{bar.value}%</span>
				</div>
			{/each}
		{/each}
	</div>
</StatCardBase>

<style>
	.bar-chart {
		display: grid;
		grid-template-columns: max-content 1fr;
		align-items: center;
		column-gap: 14px;
		row-gap: 10px;
		width: 100%;
	}

	.metric-label,
	.row-divider {
		grid-column: 1 / -1;
	}

	.row-divider {
		height: 1px;
		background-color: rgba(255, 255, 255, 0.15);
		margin: 14px 0;
	}

	.metric-label {
		font-family: RobotoBold, sans-serif;
		font-size: 18px;
		color: var(--mjWhite);
		padding-bottom: 4px;
	}

	.bar-label {
		font-family: RobotoRegular, sans-serif;
		font-size: 14px;
		color: var(--mjWhite);
		opacity: 1;
		white-space: nowrap;
	}

	@media (max-width: 550px) {
		.bar-chart {
			grid-template-columns: 1fr;
			row-gap: 6px;
		}

		.bar-label {
			white-space: normal;
			font-size: 12px;
		}

		.metric-label {
			font-size: 15px;
		}

		.pct {
			font-size: 14px;
		}
	}

	.bar-track {
		display: flex;
		align-items: center;
		height: 30px;
		background-color: rgba(255, 255, 255, 0.08);
		border-radius: 2px;
	}

	.bar {
		flex: 0 0 auto;
		align-self: stretch;
		border-radius: 2px;
	}

	.pct {
		font-family: RobotoBold, sans-serif;
		font-size: 17px;
		padding-left: 6px;
		white-space: nowrap;
		line-height: 1;
	}
</style>
