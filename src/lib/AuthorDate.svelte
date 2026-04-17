<script>
	export let authors = "";
	export let graphics = "";
	export let research = "";
	export let writing = "";
	export let date = "";
	export let credits = [];
</script>

<div class="author-date">
	<p>
		{#if authors}
			By {@html authors}
		{/if}
		{#if research}
			<br>
			<span class="role">Research:</span> {@html research}
		{/if}
		{#if graphics}
			<br>
			<span class="role">Graphics:</span> {@html graphics}
		{/if}
		{#if writing}
			<br>
			<span class="role">Writing:</span> {@html writing}
		{/if}
		{#if credits.length > 0}
			{#each credits as credit, i}
				{#if i > 0}<br>{/if}
				<span class="role">{credit.role}:</span> {credit.names}
			{/each}
		{/if}
		<br><br>
		<span class="date">{date}</span>
	</p>
</div>

<style>
	.author-date {
		max-width: 680px;
		margin: 0 auto;
		margin-bottom: 60px;
		/* padding: 0 20px 24px; */
		padding-bottom: 10px;
		border-bottom: 1px solid var(--mjPaleGrey);
	}

	.author-date p {
		font-family: RobotoRegular, sans-serif;
		font-size: 14px;
		line-height: 24px;
		color: var(--mjBlue);
		margin: 0;
	}

	@media screen and (max-width: 600px) {
		.author-date p {
			font-size: 12px;
			line-height: 20px;
		}
	}

	.role {
		font-family: RobotoBold, sans-serif;
		color: var(--mjPurple);
	}

	.date {
		font-family: RobotoBold, sans-serif;
		font-size: 13px;
		color: var(--mjBlack);
	}
</style>
