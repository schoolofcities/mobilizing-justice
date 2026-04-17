<script>
	export let footnotes;
	export let footnoteListTitle = "References";
</script>

<div class="footnotes">
	<h2>{footnoteListTitle}</h2>
	<br>

	{#each footnotes as footnote (footnote.id)}
		<div id={`footnote-${footnote.id}`} class="footnote-item">
			<sup>
				<a
					href={`#footnote-ref-${footnote.id}`}
					class="backlink"
					on:click|preventDefault={() => {
						const element = document.getElementById(`footnote-ref-${footnote.id}`);
						if (element) {
							const y = element.getBoundingClientRect().top + window.pageYOffset - 100;
							window.scrollTo({ top: y, behavior: 'auto' });
						}
					}}
				>[{footnote.id}]</a>
			</sup>
			<p style="display:inline">{@html footnote.text}</p>
			<a
				href={`#footnote-ref-${footnote.id}`}
				class="backlink"
				on:click|preventDefault={() => {
					const element = document.getElementById(`footnote-ref-${footnote.id}`);
					if (element) {
						const y = element.getBoundingClientRect().top + window.pageYOffset - 100;
						window.scrollTo({ top: y, behavior: 'auto' });
					}
				}}
			>⮝</a>
		</div>
	{/each}
</div>

<style>
	.footnotes {
		max-width: 680px;
		margin: 0 auto;
		padding: 20px 20px 32px;
		margin-top: 40px;
		margin-bottom: 50px;
		border-top: solid 1px var(--mjPaleGrey);
		border-bottom: solid 1px var(--mjPaleGrey);
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
		font-size: 15px;
		line-height: 22px;
		color: var(--mjBlack);
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
