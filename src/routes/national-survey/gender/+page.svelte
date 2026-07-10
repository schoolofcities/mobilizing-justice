
<svelte:head>
	<meta name="description" content="Key findings on gender and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta name="author" content="Jeff Allen"/>
	<meta property="og:title" content="Gender & Transport Poverty | Mobilizing Justice"/>
	<meta property="og:description" content="Key findings on gender and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta property="og:type" content="website"/>
	<meta property="og:url" content="https://schoolofcities.github.io/mobilizing-justice/national-survey/gender"/>
	<meta property="og:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<meta property="og:locale" content="en_CA"/>
	<meta name="twitter:card" content="summary_large_image"/>
	<meta name="twitter:site" content="https://schoolofcities.github.io/mobilizing-justice/national-survey/gender"/>
	<meta name="twitter:title" content="Gender & Transport Poverty | Mobilizing Justice"/>
	<meta name="twitter:description" content="Key findings on gender and transport poverty across Canada from the Mobilizing Justice National Survey"/>
	<meta name="twitter:image" content="https://schoolofcities.github.io/mobilizing-justice/web-card.png"/>
	<title>Gender | Mobilizing Justice National Survey</title>
</svelte:head>

<Password/>



<script>

	import "../../../assets/global-styles.css";
	import StatCardTable from '$lib/StatCardTable.svelte';
	import StatCardBars from '$lib/StatCardBars.svelte';
	import StatCardTwoSquares from '$lib/StatCardTwoSquares.svelte';
	import StatCardGrid from '$lib/StatCardGrid.svelte';
	import TitleText from '$lib/TitleText.svelte';
	import Password from '$lib/Password.svelte';
	import PageFooter from '$lib/PageFooter.svelte';

	import iconCar from '../../../assets/svg-icons/directions_car.svg?url';
	import iconTrain from '../../../assets/svg-icons/train.svg?url';
	import iconBuilding from '../../../assets/svg-icons/domain.svg?url';
	import iconBike from '../../../assets/svg-icons/pedal_bike.svg?url';

</script>




<TitleText
	subtitle="MJ National Survey"
	title="Gender"
	description="Key findings on gender and transport poverty across Canada"
/>

<div class="text">

	<p>
		How people get around is shaped by gender. Travel needs, safety concerns, and the barriers people face are not the same across genders. Women and non-binary people often make more complex trips and encounter greater challenges around affordability, safety, and service reliability.
	</p>
	<p>
		These findings come from the <a href="https://mobilizingjustice.ca/working-groups/national-survey-of-transport-poverty-and-trse/" target="_blank">Mobilizing Justice National Survey on Transport Poverty</a>. Women are less likely to cycle and more likely to find transportation unaffordable than men. Non-binary individuals face the sharpest barriers: lower vehicle access, higher transit reliance, and transport costs and healthcare access gaps that far exceed those reported by women and men.
	</p>

</div>



<StatCardGrid>

	<StatCardTable
		icon={iconBike}
		context="Women are less likely to bike to work or school"
		columns={[
			{ label: "Women",      color: "var(--brandLightPurple)" },
			{ label: "Men",        color: "var(--mjGreen)" },
			{ label: "Non-binary*", color: "var(--mjYellow)" }
		]}
		rows={[
			{ label: "Never bike to work",   values: [85, 70, 66] },
			{ label: "Never bike to school", values: [92, 63, 64] }
		]}
		backText="
			<p>
				Women are significantly less likely to cycle than men or non-binary individuals. 85% of women never bike to work, compared to 70% of men and 66% of non-binary individuals. Cycling to work at least once a week was also more common among non-binary individuals (over one-quarter) than among men (about one-fifth) or women (just over one-tenth).
			</p>
			<p>
				The gap is even wider for travel to school: 92% of women never bike to school, versus 63% of men and 64% of non-binary individuals. Men walk or bike to school at least once a week about 9 percentage points more than women and use bike-and-ride combinations 19 percentage points more. Non-binary individuals bike to school at considerably higher rates than both groups, nearly 29 percentage points more than women and 20 percentage points more than men. Overall, the findings suggest that women are likely to experience unique barriers to biking compared to men and non-binary individuals.
			</p>
			<p>
				Notably, women reported never biking to work even when they own at least one bike and have previously used bikeshare at a rate 15 percentage points higher than men and 19 percentage points higher than non-binary individuals. This suggests the barrier is not simply one of access. Perceived safety concerns, social norms and caregiving responsibilities appear to play a significant role, consistent with existing research on gendered experiences of cycling.			</p>
		"
	/>

	<StatCardBars
		icon={iconBuilding}
		context="Transport barriers limit access to employment and healthcare, especially for non-binary individuals"
		groups={[
			{
				label: "Agreed or strongly agreed that they have declined employment opportunities due to their transport situation (%)",
				bars: [
					{ label: "Women", value: 26 },
					{ label: "Men", value: 29 },
					{ label: "Non-binary*", value: 50 }
				]
			},
			{
				label: "Transport options enable reaching healthcare (%)",
				bars: [
					{ label: "Women", value: 73 },
					{ label: "Men", value: 72 },
					{ label: "Non-binary*", value: 50 }
				]
			}
		]}
		colors={['var(--brandLightPurple)', 'var(--mjGreen)', 'var(--mjYellow)']}
		backText="
			<p>
				Half of non-binary respondents reported that their transport situation has led them to decline employment opportunities, nearly double the rate of women (26%) and men (29%). The same share, 50%, felt that available transport options enable them to reach healthcare, compared to around 72–73% of women and men. Across both dimensions, the gap is roughly 22–24 percentage points.
			</p>
			<p>
				A key part of the context here is modal mismatch. Nearly 25% of non-binary individuals reported travelling by a mode they would not choose if alternatives were available, a noticeably higher rate than among women and men. When people are forced into transport arrangements that do not meet their needs, the downstream effects on employment access, healthcare access, and quality of life are real and compounding.
			</p>
		"
	/>



	<StatCardTwoSquares
		icon={iconCar}
		context="Non-binary individuals rely more on transit and less on private vehicles"
		sharedLabel="Respondents with access to a private vehicle (%)"
		stats={[
			{ stat: 85, color: "var(--brandLightPurple)", label: "Women" },
			{ stat: 86, color: "var(--mjGreen)",          label: "Men" },
			{ stat: 67, color: "var(--mjYellow)",         label: "Non-binary*" }
		]}
		backText="
			<p>
				Non-binary individuals reported private vehicle access nearly 19 percentage points lower than both men and women. They also hold transit passes at a rate about 13–15 percentage points higher (33%, compared to 18% of women and 20% of men), reflecting a much greater reliance on public transit for daily travel.
			</p>
			<p>
				This flows through to commuting behaviour: non-binary individuals drive to work at least once a week at rates nearly 22 percentage points lower than women and 26 percentage points lower than men, while taking transit to work at rates 12–15 percentage points higher.
			</p>
			<p>
				Non-binary individuals also reported a notably higher rate of mismatch between their most frequent and preferred travel modes (nearly 25%), suggesting that for many, this reliance on transit and active modes reflects constraint rather than choice.
			</p>
			<p>
				One striking pattern in school travel: non-binary individuals use paratransit to get to school at least once a week at rates approximately 50 percentage points higher than both women and men, one of the largest gaps observed across all groups and modes in the survey.
			</p>
		"
	/>

	<StatCardBars
		icon={iconTrain}
		context="Non-binary individuals are more likely to find transit unreliable and unaffordable"
		groups={[
			{
				label: "Find public transit reliable (%)",
				bars: [
					{ label: "Women", value: 57 },
					{ label: "Men", value: 64 },
					{ label: "Non-binary*", value: 42 }
				]
			},
			{
				label: "Spending more on transport than they can afford (%)",
				bars: [
					{ label: "Women", value: 39 },
					{ label: "Men", value: 32 },
					{ label: "Non-binary*", value: 52 }
				]
			}
		]}
		colors={['var(--brandLightPurple)', 'var(--mjGreen)', 'var(--mjYellow)']}
		backText="
			<p>
				Non-binary individuals are the least likely to trust transit. Only 42% view it as reliable, compared to 57% of women and 64% of men. This 22-point gap with men is particularly striking given that non-binary individuals rely on transit at much higher rates. When the mode you depend on most is also the one you trust least, the consequences for daily mobility are significant.
			</p>
			<p>
				The affordability picture compounds this. More than half of non-binary respondents (52%) reported spending significantly more on transportation than they can afford, compared to 39% of women and 32% of men. Women also experience greater affordability strain than men, pointing to a consistent pattern where transport costs weigh most heavily on those with the least financial flexibility. Together, these findings suggest that non-binary individuals face compounding pressures: a transit system they rely on heavily but trust least, and transport costs that strain their budgets more than any other group.
			</p>
		"
	/>




</StatCardGrid>

<div class="text">
	<p class="data-note">*Non-binary refers to respondents whose gender identity falls outside the traditional male/female binary or who selected a gender-diverse identity. This category includes responses from individuals identifying as trans man, trans woman, Two-Spirit, bigender, genderqueer, non-binary, agender, demigender, genderfluid, as well as those who preferred not to answer or selected "other" and provided a self-described identity. This grouping was created to ensure sufficient sample size and protect respondent confidentiality while recognizing the diversity of gender identities represented in the survey.</p>
</div>






<PageFooter/>

<style>
	:global(.back-text sup a:hover) {
		color: var(--mjGreen) !important;
	}
</style>