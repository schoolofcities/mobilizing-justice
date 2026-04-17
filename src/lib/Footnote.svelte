<script>
	export let id;
	let footnoteId = `footnote-${id[0]}`;
	let refId = `footnote-ref-${id[0]}`;
	let footnoteText = id[1];
	let isHovered = false;
</script>

<span class="footnote-ref-wrapper">
	<a
		id={refId}
		href={`#${footnoteId}`}
		class="footnote-ref"
		on:click|preventDefault={() => {
			const element = document.getElementById(footnoteId);
			if (element) element.scrollIntoView({ behavior: 'auto', block: 'start' });
		}}
		on:mouseenter={() => isHovered = true}
		on:mouseleave={() => isHovered = false}
	>
		<span >[{id[0]}]</span>
	</a>

	{#if isHovered}
		<div class="footnoteTooltip" on:mouseenter={() => isHovered = true} on:mouseleave={() => isHovered = false}>
			<p>[{id[0]}] {@html footnoteText}</p>
		</div>
	{/if}
</span>

<style>
	.footnote-ref-wrapper {
		position: relative;
		font-size: 1em;
		line-height: 1;
		display: inline;
		white-space: nowrap;
	}

	.footnote-ref {
		vertical-align: super;
		font-size: 13px;
		font-family: RobotoBold, sans-serif;
		font-weight: normal;
		margin-left: 3px;
		margin-right: 1px;
		text-decoration: none;
		color: var(--mjPurple);
		white-space: nowrap;
	}

	.footnote-ref:hover {
		color: var(--mjYellow);
	}

	.footnoteTooltip {
		position: absolute;
		bottom: 100%;
		left: 50%;
		transform: translateX(-50%);
		background: white;
		padding: 10px;
		border-radius: 0;
		width: 340px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
		border: 1px solid var(--mjPaleGrey);
		z-index: 1000;
		pointer-events: auto;
		user-select: text;
	}

	.footnoteTooltip p {
		padding: 0;
		margin: 0;
		font-family: RobotoRegular, sans-serif;
		font-size: 13px;
		line-height: 19px;
		color: var(--mjBlue);
		white-space: normal;
		word-wrap: break-word;
		overflow-wrap: break-word;
	}

	@media (max-width: 980px) {
		.footnoteTooltip {
			display: none !important;
		}
	}
</style>
