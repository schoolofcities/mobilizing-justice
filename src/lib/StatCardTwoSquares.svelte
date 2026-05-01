<script>
	import StatCardBase from './StatCardBase.svelte';

	export let context = '';
	export let description = '';

	export let stat1 = 75;
	export let label1 = '';
	export let color1 = 'var(--mjYellow)';

	export let stat2 = 42;
	export let label2 = '';
	export let color2 = 'var(--mjBlue)';
</script>

<StatCardBase {context} {description}>
	<div class="comparison">
		<div class="stat-block">
			<div class="top-row">
				<div class="number" style="color: {color1}">
					{stat1}%
				</div>

				<div class="grid">
					{#each Array(100) as _, i}
						<div
							class="square"
							class:filled={i < stat1}
							style="--fill: {color1};"
						/>
					{/each}
				</div>
			</div>

			<div class="sublabel">{label1}</div>
		</div>

		<div class="stat-block">
			<div class="top-row">
				<div class="number" style="color: {color2}">
					{stat2}%
				</div>

				<div class="grid">
					{#each Array(100) as _, i}
						<div
							class="square"
							class:filled={i < stat2}
							style="--fill: {color2};"
						/>
					{/each}
				</div>
			</div>

			<div class="sublabel">{label2}</div>
		</div>
	</div>
</StatCardBase>

<style>
	.comparison {
		display: flex;
		gap: 28px;
		width: 100%;
	}

	@media (max-width: 550px) {
		.comparison {
			flex-direction: column;
			gap: 24px;
		}

		.number {
			font-size: 40px;
			min-width: 74px;
		}

		.sublabel {
			font-size: 14px;
		}
	}

	.stat-block {
		flex: 1;
		display: flex;
		flex-direction: column;
		gap: 12px;
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
		min-width: 92px;
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

	.sublabel {
		font-family: RobotoBold, sans-serif;
		font-size: 17px;
		line-height: 1.3;
		color: var(--mjWhite);
		opacity: 0.92;
	}
</style>