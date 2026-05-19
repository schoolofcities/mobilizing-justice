<script>
	import StatCardBase from './StatCardBase.svelte';

	export let context = '';
	export let description = '';
	export let backText = '';
	export let icon = '';
	// columns: [{ label: string, color: string }]
	export let columns = [];
	// rows: [{ label: string, values: [number|string] }]
	export let rows = [];
	export let unit = '%';
</script>

<StatCardBase {context} {description} {backText} {icon}>
	<table>
		<thead>
			<tr>
				<th></th>
				{#each columns as col}
					<th>{col.label}</th>
				{/each}
			</tr>
		</thead>
		<tbody>
			{#each rows as row}
				<tr>
					<td class="row-label">{row.label}</td>
					{#each row.values as val, i}
						<td class="value" style="color: {columns[i].color}">{val}{unit}</td>
					{/each}
				</tr>
			{/each}
		</tbody>
	</table>
</StatCardBase>

<style>
	table {
		width: 100%;
		border-collapse: collapse;
	}

	th {
		font-family: RobotoBold, sans-serif;
		font-size: 15px;
		text-align: center;
		padding: 0 12px 10px 12px;
		border-bottom: 1px solid rgba(255, 255, 255, 0.25);
		white-space: nowrap;
		width: 1%;
	}

	th:not(:first-child) {
		color: var(--mjWhite);
	}

	th:first-child {
		text-align: left;
		color: var(--mjWhite);
		padding-left: 0;
		width: auto;
	}

	td {
		padding: 12px 12px;
		border-bottom: 1px solid rgba(255, 255, 255, 0.1);
		width: 1%;
	}

	td:first-child {
		width: auto;
	}

	tr:last-child td {
		border-bottom: none;
	}

	.row-label {
		font-family: RobotoBold, sans-serif;
		font-size: 18px;
		color: var(--mjWhite);
		padding-left: 0;
	}

	.value {
		font-family: RobotoBold, sans-serif;
		font-size: 36px;
		text-align: center;
		line-height: 1;
	}

	@media (max-width: 550px) {
		th {
			font-size: 13px;
			padding: 0 8px 8px 8px;
		}

		.row-label {
			font-size: 13px;
		}

		.value {
			font-size: 22px;
			padding: 10px 8px;
		}
	}
</style>
