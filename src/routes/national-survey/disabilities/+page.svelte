
<Password/>



<script>

	import "../../../assets/global-styles.css";
	import StatCardStack from '$lib/StatCardStack.svelte';
	import StatCardTwoSquares from '$lib/StatCardTwoSquares.svelte';
	import StatCardGrid from '$lib/StatCardGrid.svelte';
	import TitleText from '$lib/TitleText.svelte';
	import Password from "$lib/Password.svelte";
	import Footnotes from '$lib/Footnotes.svelte';

	import iconWalk from '../../../assets/svg-icons/directions_walk.svg?url';
	import iconCar from '../../../assets/svg-icons/directions_car.svg?url';
	import iconBuilding from '../../../assets/svg-icons/domain.svg?url';

	const footnotes = [
		// { id: 1, text: "" },
	];

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



<StatCardGrid maxCols={2}>

	<StatCardStack
		icon={iconWalk}
		context="Individuals with difficulties or disabilities have access to fewer transport options than they would like"
		sharedLabel="Agreed or strongly agreed that they have access to fewer transport options than they would like"
		stats={[
			{ stat: "41%", label: "Individuals with disabilities", color: "var(--mjYellow)" },
			{ stat: "29%", label: "Individuals without disabilities", color: "var(--mjGreen)" }
		]}
		backText="
			<p>
				Individuals with disabilities or difficulties reported having fewer mobility options available. The share of individuals with disabilities who agree or strongly agree to have access to fewer mobility options than desired is almost 12 percentage points higher than that of those without disabilities.
			</p>
		"
	/>

	<StatCardTwoSquares
		icon={iconCar}
		context="Road safety concerns affect individuals with disabilities more"
		sharedLabel="Agreed or strongly agreed that they feel safe from road accidents while travelling"
		stats={[
			{ stat: 38, color: "var(--mjYellow)", label: "Individuals with disabilities" },
			{ stat: 51, color: "var(--mjGreen)",  label: "Individuals without disabilities" }
		]}
		backText="
			<p>
				The share of individuals with disabilities who agree or strongly agree that they feel safe from road accidents while travelling is 13 percentage points lower than that of those without disabilities. This finding may suggest implicit ableism in built infrastructure.
			</p>
		"
	/>

	<StatCardTwoSquares
		icon={iconBuilding}
		context="Individuals with disabilities reported more inadequate access to mental health care"
		sharedLabel="Agreed or strongly agreed that they can easily reach mental health support"
		stats={[
			{ stat: 53, color: "var(--mjYellow)", label: "Individuals with disabilities" },
			{ stat: 64, color: "var(--mjGreen)",  label: "Individuals without disabilities" }
		]}
		backText="
			<p>
				The share of individuals with disabilities who agree or strongly agree that they can easily reach mental health care, support groups, or recovery meetings is 11 percentage points lower than the share among individuals without disabilities. A similar pattern is observed for access to gyms, teams, or hobby clubs, where individuals with disabilities are also 11 percentage points less likely to report easy access.
			</p>
		"
	/>

</StatCardGrid>

<Footnotes {footnotes} />

<div class="text">

	<p class="data-note">
	<span class="section-subheading">Credits</span><br><br>
		Research and writing: [TBD]<br>
		Web development and data visualization: Jeff Allen
	</p>
	<br>
	<br>
	<br>
	<br>

</div>
