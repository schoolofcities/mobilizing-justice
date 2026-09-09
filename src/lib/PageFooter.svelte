<script>
	import { base } from '$app/paths';
	import { page } from '$app/stores';
	import { nationalSurveyPages } from '$lib/nationalSurveyPages.js';
	import mjLogo from '../assets/mj-logo.png?url';
	import sofcLogo from '../assets/sofc-uoft-logo-blue-colour.svg?url';

	$: currentSlug = $page.url.pathname.replace(/\/$/, '').split('/').pop();
	$: onHub = currentSlug === 'national-survey';
	$: otherPages = nationalSurveyPages.filter(p => p.live && p.slug !== currentSlug);
</script>

<div class="footer-wrap text">
	<div class="credits-block">
		<p>
			<i>Research and writing:</i> Paromita Nakshi, Andrei Botescu, Ignacio Tiznado-Aitken and Steven Farber<br>
			<i>Data visualization:</i> Jeff Allen
		</p>
	</div>

	{#if !onHub}
		<nav class="page-nav">
			<div class="nav-heading">Explore other findings</div>
			<div class="nav-buttons">
				<a href="{base}/national-survey" class="nav-button nav-home">← All findings</a>
				{#each otherPages as p}
					<a href="{base}/national-survey/{p.slug}" class="nav-button">{p.title}</a>
				{/each}
			</div>
		</nav>
	{/if}

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

	.credits-block i {
		font-family: RobotoItalic, sans-serif;
		font-style: normal;
	}

	.page-nav {
		padding: 40px 0;
		border-top: 1px solid var(--mjPaleGrey);
	}

	.nav-heading {
		font-family: RobotoBold, sans-serif;
		font-size: 18px;
		color: var(--mjBlue);
	}

	.nav-buttons {
		display: flex;
		flex-wrap: wrap;
		gap: 12px;
		margin-top: 18px;
	}

	.nav-button {
		font-family: RobotoBold, sans-serif;
		font-size: 15px;
		letter-spacing: 0.03em;
		background-color: var(--mjWhite);
		color: var(--mjBlue);
		box-shadow: inset 0 0 0 2px var(--mjBlue);
		padding: 12px 20px;
		text-decoration: none;
		transition: background 0.15s;
	}

	.nav-button:hover {
		background-color: color-mix(in srgb, var(--mjBlue) 85%, white);
		color: var(--mjWhite);
	}

	.nav-home {
		background-color: transparent;
		color: var(--mjBlue);
		box-shadow: inset 0 0 0 2px var(--mjBlue);
	}

	.nav-home:hover {
		background-color: var(--mjBlue);
		color: var(--mjWhite);
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
