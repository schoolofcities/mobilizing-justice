
<svelte:head>
	<meta name="description" content="Key findings on age and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta name="author" content="Jeff Allen"/>
	<meta property="og:title" content="Age & Transport Poverty | Mobilizing Justice"/>
	<meta property="og:description" content="Key findings on age and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta property="og:type" content="website"/>
	<meta property="og:url" content="https://schoolofcities.github.io/mobilizing-justice/national-survey/age"/>
	<meta property="og:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<meta property="og:locale" content="en_CA"/>
	<meta name="twitter:card" content="summary_large_image"/>
	<meta name="twitter:site" content="https://schoolofcities.github.io/mobilizing-justice/national-survey/age"/>
	<meta name="twitter:title" content="Age & Transport Poverty | Mobilizing Justice"/>
	<meta name="twitter:description" content="Key findings on age and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta name="twitter:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<title>Age | Mobilizing Justice National Survey</title>
</svelte:head>

<Password/>



<script>

	import "../../../assets/global-styles.css";
	import StatCardBars from '$lib/StatCardBars.svelte';
	import StatCardTwoSquares from '$lib/StatCardTwoSquares.svelte';
	import iconBuilding from '../../../assets/svg-icons/domain.svg?url';
	import StatCardGrid from '$lib/StatCardGrid.svelte';
	import TitleText from '$lib/TitleText.svelte';
	import Password from "$lib/Password.svelte";
	import Footnote from '$lib/Footnote.svelte';
	import Footnotes from '$lib/Footnotes.svelte';
	import PageFooter from '$lib/PageFooter.svelte';

	import iconTrain from '../../../assets/svg-icons/train.svg?url';
	import iconMoney from '../../../assets/svg-icons/attach_money.svg?url';

	const footnotes = [
		// { id: 1, text: "" },
	];

</script>




<TitleText
	subtitle="MJ National Survey"
	title="Age"
	description="Key findings on age and transport poverty across Canada"
/>

<div class="text">

	<p>
		Transport poverty can affect people differently across the life course because transportation needs, resources, responsibilities, and mobility options often vary by age. Younger people may face constraints related to education, early employment, and limited access to vehicles, while older adults may experience mobility challenges linked to health, fixed incomes, or reduced driving ability. Findings from the National Survey can help identify which groups face distinct barriers to reaching jobs, services, education, and social opportunities, and supports more targeted and equitable transportation planning.
	</p>

</div>



<StatCardGrid maxCols={2}>

	<StatCardBars
		icon={iconTrain}
		context="Transit use decreases with age"
		groups={[
			{
				label: "Own a transit pass (%)",
				bars: [
					{ label: "18–24", value: 48 },
					{ label: "25–44", value: 22 },
					{ label: "45–64", value: 13 },
					{ label: "65+",   value: 12 }
				]
			},
			{
				label: "Never use public transit to work (%)",
				bars: [
					{ label: "18–24", value: 49 },
					{ label: "25–44", value: 60 },
					{ label: "45–64", value: 72 }
				]
			}
		]}
		colors={['var(--mjYellow)', 'var(--mjGreen)', 'var(--brandLightPurple)', 'var(--brandLightBlue)']}
		backText="
			<p>
				Private vehicle ownership showed a steady increase with age, with the 65+ age group reporting ownership rates more than 6 percentage points higher than the 18–24 group. In contrast, transit pass ownership decreased with age: respondents aged 65+ and 45–64 reported transit pass ownership rates approximately 36 and 35 percentage points lower, respectively, than those aged 18–24.
			</p>
			<p>
				This is consistent with public transit usage across the age groups. While 49% of individuals in 18-24 age group reported never using public transit to work, 60% in 25-44 group and 72% in 45-64 group reported the same.
			</p>
		"
	/>

	<StatCardBars
		icon={iconMoney}
		context="Transport affordability affects the youth the most"
		groups={[
			{
				label: "Agreed or strongly agreed that they spend more money on transport than they can afford (%)",
				bars: [
					{ label: "18–24", value: 45 },
					{ label: "25–44", value: 44 },
					{ label: "45–64", value: 32 },
					{ label: "65+",   value: 21 }
				]
			}
		]}
		colors={['var(--mjYellow)', 'var(--mjGreen)', 'var(--brandLightPurple)', 'var(--brandLightBlue)']}
		backText="
			<p>
				Individuals in the 18-24 and 25-44 age groups have been reported to be noticeably more affected by transport unaffordability than their older counterparts. Nearly 15% in the 18-24 age group also reported affordability issues as a key reason for not using their preferred mode more often.
			</p>
		"
	/>

	<StatCardTwoSquares
		icon={iconBuilding}
		context="Too few jobs within an ideal commuting time for the youth"
		sharedLabel="Agreed or strongly agreed that there are too few jobs within their ideal commuting time"
		stats={[
			{ stat: 55, color: "var(--mjYellow)",         label: "18–24" },
			{ stat: 50, color: "var(--mjGreen)",          label: "25–44" },
			{ stat: 42, color: "var(--brandLightPurple)", label: "45–64" }
		]}
		backText="
			<p>
				Younger individuals also reported greater difficulty accessing nearby opportunities within a reasonable travel time. Nearly 55% of individuals aged 18-24 agreed that there are too few jobs within their ideal commuting time, approximately 13 percentage points higher than the 45-64 age group. They also reported, at a similarly higher rate than those aged 45-64, that there are not enough restaurants or coffee shops within a reasonable travel time.
			</p>
			<p>
				These findings are consistent with broader patterns in travel-time dissatisfaction. While 30% of individuals aged 45-64 and 19% of those aged 65 and over agreed or strongly agreed that they spend more time travelling than they would like, the corresponding shares were much higher among younger adults: nearly 54% among those aged 18-24 and 44% among those aged 25-44. Together, these results suggest that younger individuals may experience transportation constraints not only in relation to employment and education, but also in their everyday access to services and amenities.
			</p>
			<p>
				30% of individuals aged 65+ also agreed or strongly agreed that there are too few jobs within their ideal commuting time.
			</p>
		"
	/>

	<StatCardTwoSquares
		icon={iconBuilding}
		context="Transportation barriers cost younger individuals job opportunities"
		sharedLabel="Agreed or strongly agreed that transportation constraints led them to decline employment opportunities"
		stats={[
			{ stat: 40, color: "var(--mjYellow)",         label: "18–24" },
			{ stat: 30, color: "var(--mjGreen)",          label: "25–44" },
			{ stat: 22, color: "var(--brandLightPurple)", label: "45–64" }
		]}
		backText="
			<p>
				Transportation-related constraints appear to affect employment opportunities more strongly among younger individuals. Nearly 40% of individuals aged 18-24 agreed that transportation constraints led them to decline employment opportunities. This is approximately 10 percentage points higher than the 25-44 age group and 18 percentage points higher than the 45-64 age group.
			</p>
			<p>
				In addition, over 27% of individuals aged 18-24 agreed or strongly agreed that their transportation situation led them to not pursue educational opportunities. Together, these findings suggest that transportation difficulties may have long-lasting adverse impacts on youth populations by limiting both future educational pathways and immediate and future employment opportunities.
			</p>
			<p>
				11% of individuals aged 65+ also agreed or strongly agreed that transportation constraints led them to decline employment opportunities.
			</p>
		"
	/>

</StatCardGrid>

<Footnotes {footnotes} />


<PageFooter/>
