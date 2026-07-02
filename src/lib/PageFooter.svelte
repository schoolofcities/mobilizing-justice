<script>
	import mjLogo from '../assets/mj-logo.png?url';
	import sofcLogo from '../assets/sofc-uoft-logo-blue-colour.svg?url';
</script>

<div class="footer-wrap">
	<div class="credits-block">
		<p class="data-note">
			Research and writing: Paromita Nakshi, who else?<br>
			Web development and data visualization: Jeff Allen
		</p>
	</div>

	<footer>
		<div class="logos">
			<a href="https://schoolofcities.utoronto.ca/" target="_blank" rel="noopener noreferrer">
				<img src={sofcLogo} alt="School of Cities, University of Toronto" class="sofc-logo" />
			</a>
			<a href="https://mobilizingjustice.ca/" target="_blank" rel="noopener noreferrer">
				<img src={mjLogo} alt="Mobilizing Justice" class="mj-logo" />
			</a>
		</div>
	</footer>
</div>

<style>
	.footer-wrap {
		max-width: 500px;
		width: 100%;
		margin: 100px auto 0;
		padding: 0 24px;
		box-sizing: border-box;
	}

	.credits-block {
		padding: 48px 13px 40px;
		border-top: 1px solid var(--mjPaleGrey);
	}

	footer {
		padding: 40px 0 60px;
		border-top: 1px solid var(--mjPaleGrey);
	}

	.logos {
		display: flex;
		align-items: center;
		gap: 40px;
		flex-wrap: wrap;
	}

	.mj-logo {
		height: 44px;
		width: auto;
		mix-blend-mode: multiply;
		transition: opacity 0.15s;
	}

	.sofc-logo {
		height: 48px;
		width: auto;
		transition: opacity 0.15s;
	}

	a:hover img {
		opacity: 0.75;
	}
</style>
