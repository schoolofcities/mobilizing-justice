
<svelte:head>
	<meta name="description" content="Key findings on ethnicity and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta name="author" content="Jeff Allen"/>
	<meta property="og:title" content="Ethnicity & Transport Poverty | Mobilizing Justice"/>
	<meta property="og:description" content="Key findings on ethnicity and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta property="og:type" content="website"/>
	<meta property="og:url" content="https://schoolofcities.github.io/mobilizing-justice/national-survey/ethnicity"/>
	<meta property="og:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<meta property="og:locale" content="en_CA"/>
	<meta name="twitter:card" content="summary_large_image"/>
	<meta name="twitter:site" content="https://schoolofcities.github.io/mobilizing-justice/national-survey/ethnicity"/>
	<meta name="twitter:title" content="Ethnicity & Transport Poverty | Mobilizing Justice"/>
	<meta name="twitter:description" content="Key findings on ethnicity and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta name="twitter:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<title>Ethnicity | Mobilizing Justice National Survey</title>
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

	const footnotes = [
		// { id: 1, text: "" },
	];

</script>




<TitleText
	subtitle="MJ National Survey"
	title="Ethnicity"
	description="Key findings on ethnicity and transport poverty across Canada"
/>

<div class="text">

	<p>
		Transport poverty can vary by racial and Indigenous identity because access to transportation is shaped by broader patterns of social, economic, and spatial inequality. In Canada, visible minority and Indigenous populations often experience distinct transportation barriers due to differences in income, housing location, employment opportunities, car access, transit service availability, and experiences of exclusion or discrimination. Examining transport poverty across White, visible minority, and Indigenous populations therefore helps identify whether transportation systems are meeting the needs of different communities equitably, and whether certain groups face greater barriers to reaching jobs, education, services, and social opportunities.
	</p>

</div>



<StatCardGrid maxCols={2}>

	<StatCardStack
		icon={iconTrain}
		context="Transit pass ownership is highest among visible minorities"
		sharedLabel="Percent of respondents who own a transit pass"
		stats={[
			{ stat: "14%", label: "White individuals", color: "var(--mjGreen)" },
			{ stat: "35%", label: "Visible minority individuals", color: "var(--mjYellow)" },
			{ stat: "26%", label: "Indigenous individuals", color: "var(--brandLightPurple)" }
		]}
		backText="
			<p>
				While private vehicle ownership rates are largely similar among White, visible minority, and Indigenous populations, transit pass ownership is considerably higher among visible minorities and Indigenous individuals. The share of transit pass ownership is 21 percentage points higher among visible minorities and 12 percentage points higher among Indigenous individuals compared with White individuals.
			</p>
			<p>
				However, visible minority and Indigenous individuals reported using taxis, rideshare services, and paratransit more frequently than white individuals. For instance, while just over 3% of white individuals reported using taxis or rideshare services to commute to work at least once a week, nearly 11% of visible minorities and 22% of Indigenous respondents reported doing so. This discrepancy is noteworthy given the similar patterns of private vehicle ownership across these groups and may suggest that vehicle ownership alone does not fully meet individuals' travel needs.
			</p>
		"
	/>

	<StatCardTwoSquares
		icon={iconTrain}
		context="White individuals are less likely to use public transit for commuting"
		sharedLabel="Percent of respondents who reported never using public transit to work"
		stats={[
			{ stat: 75, color: "var(--mjGreen)",          label: "White individuals" },
			{ stat: 44, color: "var(--mjYellow)",         label: "Visible minority individuals" },
			{ stat: 48, color: "var(--brandLightPurple)", label: "Indigenous individuals" }
		]}
		backText="
			<p>
				White individuals are less likely to use public transit for commuting, even when transit is available. Nearly 75% of White respondents reported never taking public transit to work, compared with 44% of visible minorities and 48% of Indigenous individuals. A somewhat similar pattern appears for school travel, where over 34% of White respondents reported never taking transit, compared with 24% of visible minorities and 39% of Indigenous individuals.
			</p>
			<p>
				Bike-and-ride commuting was also less common among white individuals. For example, the share of respondents using bike-and-ride to commute to work at least once a week was 30 percentage points higher among Indigenous respondents and 9 percentage points higher among visible minorities than among white respondents.
			</p>
		"
	/>

	<StatCardTwoSquares
		icon={iconBike}
		context="White individuals are less likely to bike to work"
		sharedLabel="Percent of respondents who reported never biking to work"
		stats={[
			{ stat: 81, color: "var(--mjGreen)",          label: "White individuals" },
			{ stat: 71, color: "var(--mjYellow)",         label: "Visible minority individuals" },
			{ stat: 55, color: "var(--brandLightPurple)", label: "Indigenous individuals" }
		]}
		backText="
			<p>
				In contrast to the common perception that a standard cyclist is a white guy in expensive gear, our findings show that visible minorities and Indigenous individuals tend to bike more than their white counterparts for both work and school travel. The share of white respondents who reported never biking to work, even after owning at least one bike or having previously used bikeshare, is nearly 10 percentage points higher than that of visible minorities and 26 percentage points higher than that of Indigenous individuals. Similar patterns are noticeable for school travel as well.
			</p>
		"
	/>

	<StatCardBars
		icon={iconBuilding}
		context="Transportation barriers cost visible minority and Indigenous individuals job opportunities"
		groups={[
			{
				label: "Agreed or strongly agreed that transportation constraints led them to decline employment opportunities (%)",
				bars: [
					{ label: "White individuals", value: 23 },
					{ label: "Visible minority individuals", value: 37 },
					{ label: "Indigenous individuals", value: 43 }
				]
			}
		]}
		colors={['var(--mjGreen)', 'var(--mjYellow)', 'var(--brandLightPurple)']}
		backText="
			<p>
				Visible minority and Indigenous respondents reported higher levels of employment-related impacts from transportation constraints. Nearly 37% of visible minority respondents and 43% of Indigenous respondents agreed or strongly agreed that transportation constraints led them to decline employment opportunities. These shares are approximately 15 and 24 percentage points higher, respectively, than the share among White respondents.
			</p>
			<p>
				A similar pattern is observed for education-related impacts, with visible minority and Indigenous respondents more likely than White respondents to report not pursuing educational opportunities because of transportation difficulties. Together, these findings suggest that transportation barriers may reinforce existing inequities by limiting access to both immediate employment opportunities and longer-term educational pathways.
			</p>
		"
	/>

</StatCardGrid>

<Footnotes {footnotes} />


<PageFooter/>
