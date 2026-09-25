
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




<script>

	import "../../../assets/global-styles.css";
	import StatCardBars from '$lib/StatCardBars.svelte';
	import StatCardDonuts from '$lib/StatCardDonuts.svelte';
	import StatCardStack from '$lib/StatCardStack.svelte';
	import StatCardTwoSquares from '$lib/StatCardTwoSquares.svelte';
	import StatCardGrid from '$lib/StatCardGrid.svelte';
	import TitleText from '$lib/TitleText.svelte';
	import Password from '$lib/Password.svelte';
	import PageFooter from '$lib/PageFooter.svelte';

	import iconTrain from '../../../assets/svg-icons/train.svg?url';
	import iconBike from '../../../assets/svg-icons/pedal_bike.svg?url';
	import iconBuilding from '../../../assets/svg-icons/domain.svg?url';

</script>




<TitleText
	subtitle="MJ National Survey"
	title="Ethnicity"
	description="Key findings on ethnicity and transport poverty across Canada"
/>

<div class="text">

	<p>
		Transport poverty can vary by racial and Indigenous identity* because access to transportation is shaped by broader patterns of social, economic, and spatial inequalities. In Canada, visible minority and Indigenous populations often experience distinct transportation barriers due to differences in income, housing location, employment opportunities, car access, transit service availability, and experiences of exclusion or discrimination. Examining transport poverty across racial and identity groups therefore helps identify whether transportation systems are meeting the needs of different communities equitably, and whether certain groups face greater barriers to reaching jobs, education, services, and social opportunities.
	</p>

</div>



<StatCardGrid>

	<StatCardStack
		icon={iconTrain}
		context="Transit pass ownership is highest among visible minorities"
		sharedLabel="Reported owning a transit pass (%)"
		stats={[
			{ stat: "14%", label: "Among White individuals", color: "var(--mjGreen)" },
			{ stat: "35%", label: "Among visible minority individuals", color: "var(--mjYellow)" },
			{ stat: "26%", label: "Among Indigenous individuals", color: "var(--brandLightPurple)" }
		]}
		backText="
			<p>
				Transit pass ownership was considerably higher among visible minority and Indigenous respondents than among White respondents. Ownership was 21 percentage points higher among visible minority respondents and 12 percentage points higher among Indigenous respondents.
			</p>
			<p>
				While private vehicle ownership rates are largely similar among White, visible minorities, and Indigenous populations, visible minority and Indigenous individuals reported using taxis, rideshare services, and paratransit more frequently than White individuals. For instance, while just over 3% of White individuals reported using taxis or rideshare services to commute to work at least once a week, nearly 11% of visible minority and 22% of Indigenous respondents reported doing so. This discrepancy is noteworthy given the similar patterns of private vehicle ownership across these groups and may suggest that vehicle ownership alone does not fully meet individuals’ travel needs.
			</p>
		"
	/>

	<StatCardDonuts
		icon={iconBuilding}
		context="Visible minority and Indigenous respondents report greater transportation and housing affordability pressures"
		sharedLabel="Reported spending more money on transport than they can afford (%)"
		stats={[
			{ stat: 35, label: "White individuals",            color: "var(--mjGreen)" },
			{ stat: 37, label: "Visible minority individuals", color: "var(--mjYellow)" },
			{ stat: 46, label: "Indigenous individuals",       color: "var(--brandLightPurple)" }
		]}
		backText="
			<p>
				A higher share of visible minority and Indigenous respondents also reported housing and transport unaffordability. The gap was particularly pronounced between White and Indigenous respondents. Among Indigenous respondents, the share reporting spending more money on housing than they can afford was 16 percentage points higher, while the share reporting spending more money on transport than they can afford was 11 percentage points higher. Visible minority and Indigenous respondents also reported lower dwelling and transportation satisfaction. Compared with White respondents, their average dwelling satisfaction was 7 and 10 points lower, respectively, while their average transportation satisfaction was 6 and 8 points lower.
			</p>
		"
	/>

	<StatCardTwoSquares
		icon={iconBike}
		context="White individuals are more likely to report never biking to work"
		sharedLabel="Respondents who reported never biking to work (%)"
		stats={[
			{ stat: 81, color: "var(--mjGreen)",          label: "White individuals" },
			{ stat: 71, color: "var(--mjYellow)",         label: "Visible minority individuals" },
			{ stat: 55, color: "var(--brandLightPurple)", label: "Indigenous individuals" }
		]}
		backText="
			<p>
				Contrary to expectations that cycling participation may be higher among White respondents, our findings show that visible minority and Indigenous individuals reported higher cycling participation than their White counterparts for both work and school travel. The share of White respondents who reported never biking to work, even after owning at least one bike or having previously used bikeshare, is nearly 10 percentage points higher than that of visible minority and 26 percentage points higher than that of Indigenous individuals. 
			</p>
		"
	/>

	<StatCardBars
		icon={iconBuilding}
		context="Transportation constraints may limit employment opportunities more for visible minorities and Indigenous respondents"
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
				Visible minority and Indigenous respondents reported higher levels of employment-related impacts from transportation constraints. Nearly 37% of visible minority respondents and 43% of Indigenous respondents agreed or strongly agreed that transportation constraints led them to decline employment opportunities. These shares are approximately 15 and 24 percentage points higher, respectively, than the share among White respondents. A similar pattern is observed for education-related impacts, with visible minority and Indigenous respondents more likely than White respondents to report not pursuing educational opportunities because of transportation difficulties. These findings suggest that transportation barriers may reinforce existing inequities by limiting access to both immediate employment opportunities and longer-term educational pathways.
			</p>
		"
	/>

</StatCardGrid>

<div class="text">
	<p class="data-note">*Survey results are presented using three ethnicity categories: Indigenous, visible minority, and White. The valid total raw sample size is 26,767, comprising 1,214 Indigenous respondents (4.5%), 5,069 visible minority respondents (18.9%), and 20,484 White respondents (76.5%). To ensure that the results are representative of the Canadian population, analyses use weighted sample sizes: 30,248,462 in total, including 1,353,475 Indigenous respondents (4.5%), 6,457,647 visible minority respondents (21.3%), and 22,437,340 White respondents (74.2%).</p>
</div>

<PageFooter/>
