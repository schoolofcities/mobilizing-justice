
<svelte:head>
	<meta name="description" content="Key findings on disabilities and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta name="author" content="Jeff Allen"/>
	<meta property="og:title" content="Difficulties & Disabilities | Mobilizing Justice"/>
	<meta property="og:description" content="Key findings on disabilities and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta property="og:type" content="website"/>
	<meta property="og:url" content="https://schoolofcities.github.io/mobilizing-justice/national-survey/disabilities"/>
	<meta property="og:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<meta property="og:locale" content="en_CA"/>
	<meta name="twitter:card" content="summary_large_image"/>
	<meta name="twitter:site" content="https://schoolofcities.github.io/mobilizing-justice/national-survey/disabilities"/>
	<meta name="twitter:title" content="Difficulties & Disabilities | Mobilizing Justice"/>
	<meta name="twitter:description" content="Key findings on disabilities and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta name="twitter:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<title>Difficulties & Disabilities | Mobilizing Justice National Survey</title>
</svelte:head>

<Password/>



<script>

	import "../../../assets/global-styles.css";
	import StatCardStack from '$lib/StatCardStack.svelte';
	import StatCardBars from '$lib/StatCardBars.svelte';
	import StatCardTwoSquares from '$lib/StatCardTwoSquares.svelte';
	import StatCardGrid from '$lib/StatCardGrid.svelte';
	import TitleText from '$lib/TitleText.svelte';
	import Password from '$lib/Password.svelte';
	import PageFooter from '$lib/PageFooter.svelte';

	import iconCar from '../../../assets/svg-icons/directions_car.svg?url';
	import iconBuilding from '../../../assets/svg-icons/domain.svg?url';
	import iconTrain from '../../../assets/svg-icons/train.svg?url';
	import iconMoney from '../../../assets/svg-icons/attach_money.svg?url';

</script>




<TitleText
	subtitle="MJ National Survey"
	title="Difficulties & Disabilities"
	description="Key findings on disability and transport poverty across Canada"
/>

<div class="text">

	<p>
		Disability is a critical lens for understanding transport poverty because barriers to transportation can directly limit access to health care, employment, education, social participation, and community supports. Even when services exist, they may not be easy to reach for people with disabilities due to physical accessibility barriers, limited transit coverage, unreliable service, cost, or safety concerns. Examining transport poverty by disability status helps identify whether transportation systems are enabling equitable access or reinforcing exclusion from essential and meaningful destinations.
	</p>

</div>



<StatCardGrid>

	<StatCardStack
		icon={iconTrain}
		context="Individuals with difficulties or disabilities have access to fewer transport options than they would like"
		sharedLabel="Agreed or strongly agreed that they have access to fewer transport options than they would like (%)"
		stats={[
			{ stat: "41%", label: "Individuals with disabilities*",    color: "var(--mjYellow)" },
			{ stat: "29%", label: "Individuals without disabilities", color: "var(--mjGreen)" }
		]}
		backText="
			<p>
				Individuals with disabilities or difficulties reported having fewer mobility options available. The share of individuals with disabilities who agree or strongly agree to have access to fewer mobility options than desired is almost 12 percentage points higher than that of those without disabilities.
			</p>
		"
	/>

	<StatCardBars
		icon={iconCar}
		context="Road safety concerns affect individuals with disabilities more"
		groups={[
			{
				label: "Agreed or strongly agreed that they feel safe from traffic-related injuries or fatalities while travelling (%)",
				bars: [
					{ label: "Individuals with disabilities*", value: 38 },
					{ label: "Individuals without disabilities", value: 51 }
				]
			}
		]}
		colors={['var(--mjYellow)', 'var(--mjGreen)']}
		backText="
			<p>
				The share of individuals with disabilities who agree or strongly agree that they feel safe from traffic-related injuries or fatalities while travelling is 13 percentage points lower than that of those without disabilities. This finding may suggest implicit ableism in built infrastructure.
			</p>
		"
	/>

	<StatCardBars
		icon={iconBuilding}
		context="Individuals with disabilities reported more inadequate access to mental health care"
		groups={[
			{
				label: "Agreed or strongly agreed that they can easily reach mental health support (%)",
				bars: [
					{ label: "Individuals with disabilities*",    value: 53 },
					{ label: "Individuals without disabilities", value: 64 }
				]
			}
		]}
		colors={['var(--mjYellow)', 'var(--mjGreen)']}
		backText="
			<p>
				The share of individuals with disabilities who agree or strongly agree that they can easily reach mental health care, support groups, or recovery meetings is 11 percentage points lower than the share among individuals without disabilities. A similar pattern is observed for access to gyms, teams, or hobby clubs, where individuals with disabilities are also 11 percentage points less likely to report easy access.
			</p>
		"
	/>

	<StatCardBars
		icon={iconMoney}
		context="Individuals with disabilities reported lower satisfaction with their current transport conditions"
		groups={[
			{
				label: "Reported high satisfaction with their current transport conditions (%)",
				bars: [
					{ label: "Individuals with disabilities*", value: 53 },
					{ label: "Individuals without disabilities", value: 64 }
				]
			}
		]}
		colors={['var(--mjYellow)', 'var(--mjGreen)']}
		backText="
			<p>
				The share of individuals with disabilities reporting high satisfaction with their current transport conditions is 11 percentage points higher than those without any disabilities. Individuals with disabilities reported at an 8 percentage point higher rate than those without disabilities that they spend more money on transportation than they can afford. Similarly, the share of individuals with disabilities self-reporting high ease in reaching necessary destinations is 11 percentage points lower than those without any disabilities.
			</p>
		"
	/>

</StatCardGrid>

<div class="text">
	<p class="data-note">*"Disability" refers to respondents who reported experiencing at least some level of long-term difficulty (lasting or expected to last six months or more) in one or more functional areas. In this dashboard, respondents were categorized as having a disability if they answered "sometimes," "often," or "always" to questions related to difficulties with seeing, hearing, physical activities and mobility, learning or concentrating, or emotional, psychological, or mental health conditions. This simplified yes/no grouping was created as a proxy to support analysis while recognizing a broad range of physical, cognitive, sensory, and mental health-related experiences.</p>
</div>

<PageFooter/>
