<script>
	import mjLogo from '../assets/mj-logo.png?url';
	import sofcLogo from '../assets/sofc-uoft-logo-blue-colour.svg?url';
</script>

<div class="footer-wrap text">
	<div class="credits-block">
		<p>
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
		margin-top: 100px;
		padding-top: 0;
	}

	.credits-block {
		padding: 48px 0 40px;
		border-top: 1px solid var(--mjPaleGrey);
	}

	.credits-block p {
		font-size: 14px;
		line-height: 21px;
		color: #555555;
		margin: 0;
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
