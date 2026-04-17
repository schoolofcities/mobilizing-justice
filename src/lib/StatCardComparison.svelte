<script>
	import StatCardBase from './StatCardBase.svelte';

	export let context = '';
	export let description = '';
	export let stat1 = '';
	export let label1 = '';
	export let color1 = 'var(--mjYellow)';
	export let stat2 = '';
	export let label2 = '';
	export let color2 = 'var(--mjYellow)';
</script>

<StatCardBase {context} {description}>
	<div class="comparison">
		<div class="stat-block">
			<div class="number" style="color: {color1}">{stat1}</div>
			<div class="sublabel">{label1}</div>
		</div>
		<div class="stat-block">
			<div class="number" style="color: {color2}">{stat2}</div>
			<div class="sublabel">{label2}</div>
		</div>
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
