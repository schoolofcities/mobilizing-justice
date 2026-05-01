
<Password/>



<script>

	import "../../../assets/global-styles.css";
	import StatCardComparison from '$lib/StatCardComparison.svelte';
	import StatCardBars from '$lib/StatCardBars.svelte';
	import StatCardTwoSquares from "$lib/StatCardTwoSquares.svelte";
	import StatCardGrid from '$lib/StatCardGrid.svelte';
	import TitleText from '$lib/TitleText.svelte';
	import AuthorDate from '$lib/AuthorDate.svelte';
	import Footnote from '$lib/Footnote.svelte';
	import Footnotes from '$lib/Footnotes.svelte';
	import Password from "$lib/Password.svelte";

	const footnotes = [
		{ id: 1, text: "Zhao, P., et al. (2018). Placeholder — full citation to be added." },
		{ id: 2, text: "Ghimire, S., & Bardaka, E. (2024). Placeholder — full citation to be added." },
		{ id: 3, text: "Nakshi, M., et al. (2025). Placeholder — full citation to be added." },
		{ id: 4, text: "Lucas, K. (2012). Placeholder — full citation to be added." },
		{ id: 5, text: "Ralph, K. (2018). Placeholder — full citation to be added." },
		{ id: 6, text: "Connaughton, J., et al. (2026). Placeholder — full citation to be added." },
	];

</script>




<TitleText
	subtitle="MJ National Survey"
	title="Gender"
	description="Key findings on gender and transport poverty across Canada"
/>

<div class="text">

	<p>
		Gender differences in travel behaviour and perceptions are important to understand because people’s travel needs, responsibilities, and safety concerns are not always the same. Women and gender-diverse people often make more complex trips, such as combining work, caregiving, errands, and appointments, and may face barriers related to personal safety, affordability, accessibility, or service reliability. Looking at these differences helps transportation planners and policymakers understand who is being underserved, where barriers are concentrated, and how policies, services, and infrastructure can be designed to support more gender-sensitive transportation planning and equitable access to work, education, care, and everyday opportunities.
	</p>

</div>



<StatCardGrid maxCols={2}>

	<StatCardBars
		context="Women are less likely to bike to work or school"
		groups={[
			{
				label: "Never bike to work (%)",
				bars: [
					{ label: "Women", value: 85 },
					{ label: "Men", value: 70 },
					{ label: "Other*", value: 66 }
				]
			},
			{
				label: "Never bike to school (%)",
				bars: [
					{ label: "Women", value: 92 },
					{ label: "Men", value: 63 },
					{ label: "Other*", value: 64 }
				]
			}
		]}
		colors={['var(--brandLightPurple)', 'var(--mjGreen)', 'var(--mjYellow)']}
		description="*Other category includes respondents who identified as trans woman, 2-spirited, bigendered, genderqueer, non-binary, agender, demigender, or genderfluid."
	/>

	<StatCardComparison
		context="Does transport situation lead to declining employment opportunities?"
		stats={[
			{ stat: "26%", color: "var(--brandLightPurple)", label: "of women agreed or strongly agreed with this statement" },
			{ stat: "29%", color: "var(--mjGreen)",        label: "of men agreed or strongly agreed with this statement" },
			{ stat: "50%", color: "var(--mjYellow)",       label: "of individuals in the 'Other' gender category agreed or strongly agreed with this statement" }
		]}
		description="'Other' category includes respondents who identified as trans woman, 2-spirited, bigendered, genderqueer, non-binary, agender, demigender, or genderfluid."
	/>

	

	<StatCardBars
		context="Individuals in the 'Other' gender category are less likely to have access to a private vehicle and more likely to own a transit pass"
		groups={[
			{
				label: "Have access to a private vehicle (%)",
				bars: [
					{ label: "Women", value: 85 },
					{ label: "Men", value: 86 },
					{ label: "Other*", value: 67 }
				]
			},
			{
				label: "Possess a transit pass (%)",
				bars: [
					{ label: "Women", value: 18 },
					{ label: "Men", value: 20 },
					{ label: "Other*", value: 33 }
				]
			}
		]}
		colors={['var(--brandLightPurple)', 'var(--mjGreen)', 'var(--mjYellow)']}
		description="*Other category includes respondents who identified as trans woman, 2-spirited, bigendered, genderqueer, non-binary, agender, demigender, or genderfluid."
	/>

	<StatCardComparison
		context="Men are more likely to consider public transit as reliable"
		stats={[
			{ stat: "57%", color: "var(--brandLightPurple)", label: "of women agreed or strongly agreed that public transit is reliable" },
			{ stat: "64%", color: "var(--mjGreen)",        label: "of men agreed or strongly agreed  that public transit is reliable" },
			{ stat: "42%", color: "var(--mjYellow)",       label: "of individuals in the 'Other' gender category agreed or strongly agreed that public transit is reliable" }
		]}
		description="*Other category includes respondents who identified as trans woman, 2-spirited, bigendered, genderqueer, non-binary, agender, demigender, or genderfluid."
	/>

	<StatCardComparison
		context="Women and 'Other' gender individuals are more likely to find transportation unaffordable"
		stats={[
			{ stat: "39%", color: "var(--brandLightPurple)", label: "of women reported spending significantly more money on transportation than they can afford" },
			{ stat: "32%", color: "var(--mjGreen)",        label: "of men reported spending significantly more money on transportation than they can afford" },
			{ stat: "52%", color: "var(--mjYellow)",       label: "of individuals in the 'Other' gender category reported spending significantly more money on transportation than they can afford" }
		]}
		description="*Other category includes respondents who identified as trans woman, 2-spirited, bigendered, genderqueer, non-binary, agender, demigender, or genderfluid."
	/>

	<StatCardComparison
		context="Do available transportation options enable reaching healthcare?"
		stats={[
			{ stat: "73%", color: "var(--brandLightPurple)", label: "of women agreed or strongly agreed with this statement" },
			{ stat: "72%", color: "var(--mjGreen)",        label: "of men agreed or strongly agreed with this statement" },
			{ stat: "50%", color: "var(--mjYellow)",       label: "of individuals in the 'Other' gender category agreed or strongly agreed with this statement" }
		]}
		description="*Other category includes respondents who identified as trans woman, 2-spirited, bigendered, genderqueer, non-binary, agender, demigender, or genderfluid."
	/>

	

</StatCardGrid>


<div class="text">

	<!-- <AuthorDate
		date="May 2026"
		credits={[
			{ role: "Research", names: "Author names" },
			{ role: "Writing", names: "Author names" },
			{ role: "Graphics", names: "Author names" }
		]}
	/> -->

	
	
</div>

<!-- <Footnotes {footnotes} /> -->