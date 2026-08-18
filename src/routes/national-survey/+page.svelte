
<script>
	import "../../assets/global-styles.css";
	import { base } from '$app/paths';
	import { nationalSurveyPages } from '$lib/nationalSurveyPages.js';
	import PageFooter from '$lib/PageFooter.svelte';
	import Password from '$lib/Password.svelte';
</script>

<Password/>

<svelte:head>
	<meta name="description" content="Key findings from the Mobilizing Justice National Survey on Transport Poverty in Canada"/>
	<meta name="author" content="Jeff Allen"/>
	<meta property="og:title" content="National Survey | Mobilizing Justice"/>
	<meta property="og:description" content="Key findings from the Mobilizing Justice National Survey on Transport Poverty in Canada"/>
	<meta property="og:type" content="website"/>
	<meta property="og:url" content="https://schoolofcities.github.io/mobilizing-justice/national-survey"/>
	<meta property="og:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<meta property="og:locale" content="en_CA"/>
	<meta name="twitter:card" content="summary_large_image"/>
	<meta name="twitter:site" content="https://schoolofcities.github.io/mobilizing-justice/national-survey"/>
	<meta name="twitter:title" content="National Survey | Mobilizing Justice"/>
	<meta name="twitter:description" content="Key findings from the Mobilizing Justice National Survey on Transport Poverty in Canada"/>
	<meta name="twitter:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<title>National Survey | Mobilizing Justice</title>
</svelte:head>

<div class="page-header">
	<div class="subtitle">MJ National Survey</div>
	<h1>Key findings from the Mobilizing Justice National Survey on Transport Poverty</h1>
</div>

<div class="card-grid">
	{#each nationalSurveyPages as page}
		{#if page.live}
			<a href="{base}/national-survey/{page.slug}" class="page-card">
				<div class="card-title">{page.title}</div>
				<p class="card-text">{page.text}</p>
				<span class="card-link"><span class="card-link-text">View findings</span> →</span>
			</a>
		{:else}
			<div class="page-card coming-soon">
				<div class="coming-soon-badge">Coming soon</div>
				<div class="card-title">{page.title}</div>
				<p class="card-text">{page.text}</p>
				<span class="card-link"><span class="card-link-text">View findings</span> →</span>
			</div>
		{/if}
	{/each}
</div>

<PageFooter/>

<style>
	.page-header {
		max-width: 744px;
		margin: 60px auto 60px;
		border-left: 12px solid var(--mjYellow);
		padding-left: 36px;
	}

	.subtitle {
		font-family: RobotoRegular, sans-serif;
		font-size: 20px;
		color: var(--mjPurple);
		margin-bottom: 18px;
	}

	.page-header h1 {
		font-family: RobotoBold, sans-serif;
		font-size: 36px;
		color: var(--mjBlue);
		margin: 0;
		padding: 0;
	}

	.card-grid {
		max-width: 1420px;
		margin: 0 auto;
		padding: 32px 24px 80px;
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(360px, 1fr));
		gap: 24px;
	}

	.page-card {
		background-color: var(--mjBlue);
		padding: 40px 40px 32px;
		text-decoration: none;
		display: flex;
		flex-direction: column;
		gap: 16px;
		transition: background 0.15s;
	}

	.page-card:hover {
		background-color: color-mix(in srgb, var(--mjBlue) 85%, white);
	}

	.page-card.coming-soon {
		position: relative;
		opacity: 0.2;
		cursor: default;
	}

	.page-card.coming-soon:hover {
		background-color: var(--mjBlue);
	}

	.coming-soon-badge {
		position: absolute;
		top: 16px;
		right: 16px;
		background-color: var(--mjWhite);
		color: var(--mjBlue);
		font-family: RobotoBold, sans-serif;
		font-size: 12px;
		letter-spacing: 0.05em;
		text-transform: uppercase;
		padding: 6px 12px;
		border-radius: 999px;
		opacity: calc(1 / 0.2);
	}

	.card-title {
		font-family: RobotoBold, sans-serif;
		font-size: 26px;
		color: var(--mjWhite);
		padding-bottom: 14px;
		border-bottom: solid 2px rgba(255, 255, 255, 1);
		line-height: 1.2;
	}

	.card-text {
		font-family: RobotoRegular, sans-serif;
		font-size: 15px;
		line-height: 1.6;
		color: var(--mjWhite);
		margin: 0;
		flex: 1;
	}

	.card-link {
		font-family: RobotoBold, sans-serif;
		font-size: 16px;
		color: var(--mjGreen);
		letter-spacing: 0.03em;
		margin-top: 8px;
	}

	.card-link-text {
		text-decoration: underline;
		text-underline-offset: 3px;
	}

	@media (max-width: 600px) {
		.card-grid {
			grid-template-columns: 1fr;
			padding: 24px 16px 60px;
		}

		.page-card {
			padding: 28px 28px 24px;
		}

		.card-title {
			font-size: 22px;
		}
	}
</style>
