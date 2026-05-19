<script>
	import StatCardBase from './StatCardBase.svelte';

	export let context = '';
	export let description = '';
	export let backText = '';
	export let sharedLabel = '';
	export let icon = '';

	// stats: [{ stat, label, color }]
	export let stats = [];

	// Legacy two-item props
	export let stat1 = null;
	export let label1 = '';
	export let color1 = 'var(--mjYellow)';
	export let stat2 = null;
	export let label2 = '';
	export let color2 = 'var(--mjGreen)';

	$: items = stats.length
		? stats
		: [
				{ stat: stat1, label: label1, color: color1 },
				{ stat: stat2, label: label2, color: color2 }
		  ];
</script>

<StatCardBase {context} {description} {backText} {icon}>
	<div class="stack">
		{#if sharedLabel}
			<p class="shared-label">{sharedLabel}</p>
		{/if}
		<div class="comparison" class:three-items={items.length >= 3}>
			{#each items as item}
				<div class="stat-block">
					<div class="top-row">
						<div class="number" style="color: {item.color}">
							{item.stat}%
						</div>
						<div class="grid">
							{#each Array(100) as _, i}
								<div
									class="square"
									class:filled={i < item.stat}
									style="--fill: {item.color};"
								/>
							{/each}
						</div>
					</div>
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

	.comparison {
		display: flex;
		gap: 28px;
		width: 100%;
	}

	.stat-block {
		flex: 1;
		display: flex;
		flex-direction: column;
		gap: 10px;
	}

	.top-row {
		display: flex;
		align-items: center;
		gap: 16px;
	}

	.number {
		font-family: RobotoBold, sans-serif;
		font-size: 50px;
		line-height: 1;
		letter-spacing: -1px;
		white-space: nowrap;
		min-width: 80px;
	}

	.grid {
		display: grid;
		grid-template-columns: repeat(10, 6px);
		grid-template-rows: repeat(10, 6px);
		gap: 2px;
		padding-top: 2px;
	}

	.square {
		width: 6px;
		height: 6px;
		border-radius: 1px;
		background: rgba(255, 255, 255, 0.1);
	}

	.square.filled {
		background: var(--fill);
		box-shadow: 0 0 4px color-mix(in srgb, var(--fill) 40%, transparent);
	}

	.group-label {
		font-family: RobotoBold, sans-serif;
		font-size: 15px;
		color: var(--mjWhite);
		letter-spacing: 0.03em;
	}

	/* 3-item layout: stack number above grid */
	.three-items .top-row {
		flex-direction: column;
		align-items: flex-start;
		gap: 8px;
	}

	.three-items .number {
		font-size: 44px;
		min-width: unset;
	}

	.three-items .grid {
		grid-template-columns: repeat(10, 7px);
		grid-template-rows: repeat(10, 7px);
		gap: 2px;
	}

	.three-items .square {
		width: 7px;
		height: 7px;
	}

	@media (max-width: 550px) {
		.comparison:not(.three-items) {
			flex-direction: column;
			gap: 24px;
		}

		.number {
			font-size: 40px;
			min-width: 68px;
		}

		.three-items {
			flex-direction: row;
			flex-wrap: wrap;
			gap: 20px;
		}

		.three-items .stat-block {
			flex: 1 1 auto;
		}

		.three-items .stat-block:last-child {
			flex: 0 0 100%;
		}

		.three-items .number {
			font-size: 36px;
			min-width: unset;
		}

		.three-items .grid {
			grid-template-columns: repeat(10, 6px);
			grid-template-rows: repeat(10, 6px);
		}

		.three-items .square {
			width: 6px;
			height: 6px;
		}

		.shared-label {
			font-size: 15px;
		}
	}
</style>
