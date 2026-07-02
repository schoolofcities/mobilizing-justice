
<svelte:head>
	<meta name="description" content="Key findings on immigration status and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta name="author" content="Jeff Allen"/>
	<meta property="og:title" content="Immigration Status & Transport Poverty | Mobilizing Justice"/>
	<meta property="og:description" content="Key findings on immigration status and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta property="og:type" content="website"/>
	<meta property="og:url" content="https://schoolofcities.github.io/mobilizing-justice/national-survey/immigration"/>
	<meta property="og:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<meta property="og:locale" content="en_CA"/>
	<meta name="twitter:card" content="summary_large_image"/>
	<meta name="twitter:site" content="https://schoolofcities.github.io/mobilizing-justice/national-survey/immigration"/>
	<meta name="twitter:title" content="Immigration Status & Transport Poverty | Mobilizing Justice"/>
	<meta name="twitter:description" content="Key findings on immigration status and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta name="twitter:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<title>Immigration Status | Mobilizing Justice National Survey</title>
</svelte:head>

<Password/>



<script>

	import "../../../assets/global-styles.css";
	import StatCardBars from '$lib/StatCardBars.svelte';
	import StatCardStack from '$lib/StatCardStack.svelte';
	import StatCardTwoSquares from '$lib/StatCardTwoSquares.svelte';
	import StatCardGrid from '$lib/StatCardGrid.svelte';
	import TitleText from '$lib/TitleText.svelte';
	import Password from "$lib/Password.svelte";
	import Footnote from '$lib/Footnote.svelte';
	import Footnotes from '$lib/Footnotes.svelte';
	import PageFooter from '$lib/PageFooter.svelte';

	import iconTrain from '../../../assets/svg-icons/train.svg?url';
	import iconBike from '../../../assets/svg-icons/pedal_bike.svg?url';
	import iconBuilding from '../../../assets/svg-icons/domain.svg?url';
	import iconCar from '../../../assets/svg-icons/directions_car.svg?url';

	const footnotes = [
		// { id: 1, text: "" },
	];

</script>




<TitleText
	subtitle="MJ National Survey"
	title="Immigration Status"
	description="Key findings on immigration status and transport poverty across Canada"
/>

<div class="text">

	<p>
		Transport poverty can also vary by immigration status because transportation needs and constraints may change with settlement stage, employment conditions, social networks, housing location, and familiarity with local transportation systems. Recent immigrants may face distinct barriers as they navigate new job markets, education systems, services, and transit networks, while long-term immigrants may experience transportation challenges differently as their resources, routines, and neighbourhood ties evolve over time. Findings from the National Survey, therefore, can help identify whether transportation systems support equitable access to opportunities across different stages of settlement and integration.
	</p>

</div>



<StatCardGrid maxCols={2}>

	<StatCardStack
		icon={iconTrain}
		context="Transit pass ownership is highest among recent immigrants"
		sharedLabel="Percent of respondents who own a transit pass"
		stats={[
			{ stat: "16%", label: "Canadian born", color: "var(--mjGreen)" },
			{ stat: "48%", label: "Recent immigrants", color: "var(--mjYellow)" },
			{ stat: "24%", label: "Long-term immigrants", color: "var(--brandLightPurple)" }
		]}
		backText="
			<p>
				Recent immigrants are more likely to own transit passes, with rates 32 and 24 percentage points higher than those of Canadian-born and long-term immigrants, respectively. On the other hand, private vehicle ownership is largely similar between Canadian-born and long-term immigrant households. In contrast, the share of recent immigrant households owning private vehicles is 17 percentage points lower than that of Canadian-born households and 19 percentage points lower than that of long-term immigrant households.
			</p>
		"
	/>

	<StatCardTwoSquares
		icon={iconTrain}
		context="Canadian born individuals are less likely to use public transit for commuting"
		sharedLabel="Percent of respondents who reported using public transit to work at least once a week"
		stats={[
			{ stat: 24, color: "var(--mjGreen)",          label: "Canadian born" },
			{ stat: 59, color: "var(--mjYellow)",         label: "Recent immigrants" },
			{ stat: 38, color: "var(--brandLightPurple)", label: "Long-term immigrants" }
		]}
		backText="
			<p>
				Recent immigrants also reported walking, biking, and using public transit to commute to work at least once a week more frequently, and driving less frequently, than the other two groups. For example, the share of recent immigrants who reported taking public transit to work at least once a week is 35 percentage points higher than that of Canadian-born respondents. These patterns suggest that recent immigrants rely more heavily on public and active transportation for travelling to work, likely reflecting differences in vehicle access, settlement locations, and early adaptation to local transportation systems.
			</p>
			<p>
				Recent immigrants use public transit at a similarly high rate for trips to school. However, long-term immigrants bike more to school than the other two groups. For example, the share of long-term immigrants who bike to school at least once a week is 15 percentage points higher than that of recent immigrants and 21 percentage points higher than that of Canadian-born individuals.
			</p>
		"
	/>

	<StatCardBars
		icon={iconBuilding}
		context="Transportation barriers cost recent immigrants job opportunities"
		groups={[
			{
				label: "Agreed or strongly agreed that transportation constraints led them to decline employment opportunities (%)",
				bars: [
					{ label: "Canadian born", value: 26 },
					{ label: "Recent immigrants", value: 45 },
					{ label: "Long-term immigrants", value: 29 }
				]
			}
		]}
		colors={['var(--mjGreen)', 'var(--mjYellow)', 'var(--brandLightPurple)']}
		backText="
			<p>
				Recent immigrants reported higher agreement that transport constraints led them to decline employment opportunities. Nearly 45% of recent immigrants agreed or strongly agreed that transportation constraints led them to decline employment opportunities. These shares are approximately 19 and 16 percentage points higher than Canadian born and long term immigrants, respectively. The patterns are similar when it comes to not pursuing education due to transport constraints.
			</p>
		"
	/>

	<StatCardBars
		icon={iconCar}
		context="Recent immigrants are more likely to feel forced to use public transit"
		groups={[
			{
				label: "Agreed or strongly agreed that they feel forced to use transit (%)",
				bars: [
					{ label: "Canadian born", value: 18 },
					{ label: "Recent immigrants", value: 43 },
					{ label: "Long-term immigrants", value: 23 }
				]
			}
		]}
		colors={['var(--mjGreen)', 'var(--mjYellow)', 'var(--brandLightPurple)']}
		backText="
			<p>
				Recent immigrants report using active and public transportation more frequently than the other two groups, while also reporting a stronger sense that their use of these modes is forced. For example, over 43% of recent immigrants reported a high sense of perceived forced public transit use, whereas only 18% of Canadian-born and 23% of long-term immigrant respondents reported the same.
			</p>
			<p>
				Interestingly, recent immigrants were also more likely to perceive public transit as reliable, affordable, and time-saving. The share of recent immigrants who perceived public transit as very affordable is 13 percentage points higher than that of Canadian-born respondents and 8 percentage points higher than that of long-term immigrants. Similarly, the shares reporting transit as very reliable are 8 and 6 percentage points higher, respectively, while the shares reporting transit as very time-saving are 18 and 10 percentage points higher. These patterns suggest that recent immigrants may view public transit positively in terms of service attributes, yet still perceive their reliance on it as suboptimal.
			</p>
		"
	/>

</StatCardGrid>

<Footnotes {footnotes} />


<PageFooter/>
