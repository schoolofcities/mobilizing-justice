<script>
	// maxCols: desktop column count (default 3)
	// breakpoints: 1 col on mobile, 2 cols on tablet, maxCols on desktop
	
</script>

<div class="grid-container">
	<slot />
</div>

<style>
	.grid-container {
		column-count: 1;
		column-gap: 40px;
		width: 100%;
		max-width: 1400px;
		margin: 40px auto;
		padding: 0 40px;
		box-sizing: border-box;
		column-count: 2;
		border-top: solid 1px var(--mjPaleGrey);
		padding-top: 50px;
		padding-bottom: 50px;
		border-bottom: solid 1px var(--mjPaleGrey);
	}

	@media (min-width: 600px) {
		.grid-container {
			column-count: 2;
		}
	}

	@media (max-width: 1000px) {
		.grid-container {
			column-count: 1;
		}
	}

	.grid-container :global(.stat-card) {
		width: 100%;
		margin-top: 0;
		margin-bottom: 40px;
		break-inside: avoid;
	}
</style>
