<script>
	import StatCardBase from './StatCardBase.svelte';

	export let context = '';
	export let description = '';

	// Array API: [{ stat, label, color }]
	export let stats = [];

	// Legacy two-item props — used when stats array is not provided
	export let stat1 = '';
	export let label1 = '';
	export let color1 = 'var(--mjYellow)';
	export let stat2 = '';
	export let label2 = '';
	export let color2 = 'var(--mjYellow)';

	$: items = stats.length
		? stats
		: [
				{ stat: stat1, label: label1, color: color1 },
				{ stat: stat2, label: label2, color: color2 }
		  ];
</script>

<StatCardBase {context} {description}>
	<div class="comparison">
		{#each items as item}
			<div class="stat-block">
				<div class="number" style="color: {item.color}">{item.stat}</div>
				<div class="sublabel">{item.label}</div>
			</div>
		{/each}
	</div>
</StatCardBase>

<style>
	.comparison {
		display: flex;
		align-items: flex-start;
		justify-content: flex-start;
		gap: 32px;
		width: 100%;
	}

	@media (max-width: 550px) {
		.comparison {
			flex-direction: column;
			gap: 24px;
		}

		.number {
			font-size: 63px;
		}

		.sublabel {
			font-size: 15px;
		}
	}

	.stat-block {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		gap: 8px;
		flex: 1;
	}

	.number {
		font-family: RobotoBold, sans-serif;
		font-size: 79px;
		line-height: 1;
		letter-spacing: -1px;
	}

	.sublabel {
		font-family: RobotoBold, sans-serif;
		font-size: 18px;
		color: var(--mjWhite);
		text-align: left;
	}
</style>
