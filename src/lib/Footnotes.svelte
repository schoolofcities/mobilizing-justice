<script>
	export let footnotes;
	export let footnoteListTitle = "References";
</script>

{#if footnotes.length > 0}
<div class="footnotes">
	<h2>{footnoteListTitle}</h2>
	<br>

	{#each footnotes as footnote (footnote.id)}
		<div id={`footnote-${footnote.id}`} class="footnote-item">
			<sup>[{footnote.id}]</sup>
			<p style="display:inline">{@html footnote.text}</p>
		</div>
	{/each}
</div>
{/if}

<style>
	.footnotes {
		max-width: 780px;
		margin: 0 auto;
		padding: 20px 20px 32px;
		margin-top: 40px;
		margin-bottom: 50px;
		border-top: solid 1px var(--mjPaleGrey);
		border-bottom: solid 1px var(--mjPaleGrey);
	}

	.footnotes :global(h2) {
		font-size: 18px;
		margin-top: 0;
	}

	.footnote-item {
		padding-left: 32px;
		margin-top: 10px;
		position: relative;
	}

	.footnote-item sup {
		position: absolute;
		font-size: 13px;
		font-family: RobotoBold, sans-serif;
		font-weight: normal;
		left: 0;
	}

	.footnote-item p {
		font-family: RobotoRegular, sans-serif;
		font-size: 14px;
		line-height: 21px;
		color: #555555;
		font-weight: normal;
		margin-left: -5px;
	}

	.backlink {
		margin-left: 3px;
		font-family: RobotoBold, sans-serif;
		font-weight: normal;
		text-decoration: none;
		color: var(--mjPurple);
	}

	.backlink:hover {
		color: var(--mjYellow);
	}

	@media screen and (max-width: 600px) {
		.footnote-item p {
			font-size: 13px;
			line-height: 20px;
		}
	}

</style>
