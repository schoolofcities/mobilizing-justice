<script>
	import StatCardBase from './StatCardBase.svelte';

	export let context = '';
	export let description = '';
	export let backText = '';
	export let icon = '';
	export let sharedLabel = '';

	// stats: [{ stat, label, color }]
	export let stats = [];

	const SIZE = 120;
	const STROKE = 30;
	const FILL_STROKE = 20;
	const R = (SIZE - STROKE) / 2;
	const CIRC = 2 * Math.PI * R;
</script>

<StatCardBase {context} {description} {backText} {icon}>
	<div class="donut-wrap">
		{#if sharedLabel}
			<p class="shared-label">{sharedLabel}</p>
		{/if}
		<div class="donuts">
			{#each stats as item}
				{@const pct = Math.min(100, Math.max(0, item.stat))}
				{@const dash = (pct / 100) * CIRC}
				{@const gap = CIRC - dash}
				<div class="donut-block">
					<svg width={SIZE} height={SIZE} viewBox="0 0 {SIZE} {SIZE}">
						<!-- track -->
						<circle
							cx={SIZE / 2} cy={SIZE / 2} r={R}
							fill="none"
							stroke="rgba(255,255,255,0.1)"
							stroke-width={STROKE}
						/>
						<!-- fill -->
						<circle
							cx={SIZE / 2} cy={SIZE / 2} r={R}
							fill="none"
							stroke={item.color}
							stroke-width={FILL_STROKE}
							stroke-dasharray="{dash} {gap}"
							stroke-linecap="butt"
							transform="rotate(-90 {SIZE / 2} {SIZE / 2})"
						/>
						<text
							x={SIZE / 2} y={SIZE / 2}
							text-anchor="middle"
							dominant-baseline="central"
							font-family="RobotoBold, sans-serif"
							font-size="19"
							fill={item.color}
						>{pct}%</text>
					</svg>
					<div class="group-label">{item.label}</div>
				</div>
			{/each}
		</div>
	</div>
</StatCardBase>

<style>
	.donut-wrap {
		display: flex;
		flex-direction: column;
		gap: 20px;
		width: 100%;
	}

	.donuts {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		gap: 16px;
		align-items: flex-start;
	}

	@container (max-width: 550px) {
		.donuts {
			grid-template-columns: repeat(2, 1fr);
		}
	}

	.donut-block {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 8px;
		flex: 1;
		min-width: 70px;
	}

	.group-label {
		text-align: center;
	}
</style>
