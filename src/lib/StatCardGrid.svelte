<script>
	// maxCols: desktop column count (default 3)
	// breakpoints: 1 col on mobile, 2 cols on tablet, maxCols on desktop
	
</script>

<div class="grid-container">
	<slot />
</div>

<style>
	.grid-container {
		column-count: 2;
		column-gap: 40px;
		width: 100%;
		max-width: 1400px;
		margin: 40px auto;
		padding: 0 40px;
		box-sizing: border-box;
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

	@media (max-width: 550px) {
		.grid-container {
			padding: 0 5px;
			border-top: none;
			border-bottom: none;
		}
	}

	.grid-container :global(.flip-container),
	.grid-container :global(.stat-card) {
		width: 100%;
		margin-top: 0;
		margin-bottom: 40px;
		break-inside: avoid;
	}
</style>
