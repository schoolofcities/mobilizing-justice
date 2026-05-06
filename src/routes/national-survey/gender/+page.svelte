
<Password/>



<script>

	import "../../../assets/global-styles.css";
	import StatCardComparison from '$lib/StatCardComparison.svelte';
	import StatCardStack from '$lib/StatCardStack.svelte';
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

	<StatCardStack
		context="Does transport situation lead to declining employment opportunities?"
		sharedLabel="Percent that agreed or strongly agreed that their transport situation has led them to decline employment opportunities"
		stats={[
			{ stat: "26%", color: "var(--brandLightPurple)", label: "Women" },
			{ stat: "29%", color: "var(--mjGreen)",          label: "Men" },
			{ stat: "50%", color: "var(--mjYellow)",         label: "Other*" }
		]}
		description="*Other category includes respondents who identified as trans woman, 2-spirited, bigendered, genderqueer, non-binary, agender, demigender, or genderfluid."
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

	<StatCardStack
		context="Men are more likely to consider public transit as reliable"
		sharedLabel="Percent of respondents that agreed or strongly agreed that public transit is reliable"
		stats={[
			{ stat: "57%", color: "var(--brandLightPurple)", label: "Women" },
			{ stat: "64%", color: "var(--mjGreen)",          label: "Men" },
			{ stat: "42%", color: "var(--mjYellow)",         label: "Other*" }
		]}
		description="*Other category includes respondents who identified as trans woman, 2-spirited, bigendered, genderqueer, non-binary, agender, demigender, or genderfluid."
	/>

	<StatCardStack
		context="Women and 'Other' gender individuals are more likely to find transportation unaffordable"
		sharedLabel="Percent that reported spending significantly more money on transportation than they can afford"
		stats={[
			{ stat: "39%", color: "var(--brandLightPurple)", label: "Women" },
			{ stat: "32%", color: "var(--mjGreen)",          label: "Men" },
			{ stat: "52%", color: "var(--mjYellow)",         label: "Other*" }
		]}
		description="*Other category includes respondents who identified as trans woman, 2-spirited, bigendered, genderqueer, non-binary, agender, demigender, or genderfluid."
	/>

	<StatCardStack
		context="Do available transportation options enable reaching healthcare?"
		sharedLabel="Percent that agreed or strongly agreed that available transportation options enable them to reach healthcare"
		stats={[
			{ stat: "73%", color: "var(--brandLightPurple)", label: "Women" },
			{ stat: "72%", color: "var(--mjGreen)",          label: "Men" },
			{ stat: "50%", color: "var(--mjYellow)",         label: "Other*" }
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

	<p>
		Individuals in the 'Other' gender category reported nearly 19 percentage points lower private vehicle ownership than both men and women. In contrast, they reported higher transit pass ownership- about 13 percentage points higher than men and 15 percentage points higher than women. They also experienced a mismatch between their frequent and preferred travel modes at a noticeably higher rate (nearly 25%).
	</p>
	<p>
		Similar patterns were observed in commuting behaviour. The share of individuals who drive to work at least once a week is nearly 22 percentage points lower than among women and nearly 26 percentage points lower than among men, while the share who take transit to work at least once a week is nearly 15 percentage points higher than among women and over 12 percentage points higher than among men. Cycling to work at least once a week was more common among individuals in the 'Other' category (over one-fourth) and men (about one-fifth) than among women (just over one-tenth). Along that line, women also reported never biking to work even when they have at least one bike and used bikeshare previously at a noticeably higher rate- 15 percentage points higher than men and 19 percentage points higher than those in 'Other' gender category. This finding is consistent with previous studies on gendered experiences of cycling (Ravensbergen, 2022).
	</p>
	<p>
		The share of individuals who have taken paratransit to work at least once a week is nearly 15 percentage points lower among 'Other' gender category than both men and women. The share of individuals who never drive to work was higher among those in the 'Other' gender category- about 16 percentage points higher than women and 20 percentage points higher than men.
	</p>
	<p>
		Overall, the findings indicate that individuals in the 'Other' gender category rely more on active and public transportation and less on driving for commuting purposes. Women and men, by comparison, exhibit broadly similar travel behaviour patterns, except for significantly lower cycling rates among women.
	</p>
	<p>
		Unlike commuting patterns, gender differences among men and women are more pronounced for travel to school, with men walking or biking at least a week about 9 percentage points more than women. Men also reported travelling to school as a car passenger at least once a week about 14 percentage points more than women, and using transit nearly 22 percentage points more. Similarly, the share of men using a combination of bike and ride to school at least once a week was 19 percentage points higher than women. Men also used taxi or ride hailing at a rate 12 percentage points higher than women.
	</p>
	<p>
		Individuals in the 'Other' gender category bike to school at considerably higher rates than both men and women- nearly 29 percentage points higher than women and 20 percentage points higher than men. They report driving to school about 7 percentage points more than women but travelling as a car passenger 8 percentage points less than women and nearly 23 percentage points less than men. They also use public transit more regularly than women (9 percentage points higher) but less regularly than men (12 percentage points lower). Individuals in the 'Other' gender category report using paratransit to travel to school at least once a week at rates about 50 percentage points higher than women and 49 percentage points higher than men, representing one of the largest differences across groups.
	</p>
	<p>
		More women reported never walking to school- about 8 percentage points higher than men and 31 percentage points higher than individuals in the 'Other' category. However, women also reported walking to school four times a week at rates about 8 percentage points higher than men and 12 percentage points higher than those in the 'Other' category. A similar pattern is observed for car travel to school. While a higher share of women than men and individuals in the 'Other' category reported never driving to school or travelling as a car passenger, women also reported driving to school or travelling as a car passenger three, four or five times a week at higher rates than both men and those in the 'Other' category (by about 4 to 8 percentage points). This pattern suggests that women who walk or travel by car to school are more likely to do so more consistently than men and individuals in the 'Other' category. A similar pattern of consistency is observed for public transit and park-and-ride travel to school among women compared with those in the 'Other' category.
	</p>


</div>

<!-- <Footnotes {footnotes} /> -->