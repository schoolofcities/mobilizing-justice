
<Password/>



<script>

	import "../../../assets/global-styles.css";
	import StatCardTable from '$lib/StatCardTable.svelte';
	import StatCardBars from '$lib/StatCardBars.svelte';
	import StatCardTwoSquares from '$lib/StatCardTwoSquares.svelte';
	import StatCardGrid from '$lib/StatCardGrid.svelte';
	import TitleText from '$lib/TitleText.svelte';
	import Password from "$lib/Password.svelte";

	import iconCar from '../../../assets/svg-icons/directions_car.svg?url';
	import iconTrain from '../../../assets/svg-icons/train.svg?url';
	import iconBuilding from '../../../assets/svg-icons/domain.svg?url';
	import iconBike from '../../../assets/svg-icons/pedal_bike.svg?url';

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
		How people get around is shaped by gender. Travel needs, safety concerns, and the barriers people face are not the same across genders. Women and non-binary people often make more complex trips and encounter greater challenges around affordability, safety, and service reliability.
	</p>
	<p>
		These findings come from the <a href="https://mobilizingjustice.ca/working-groups/national-survey-of-transport-poverty-and-trse/" target="_blank">Mobilizing Justice National Survey on Transport Poverty</a>. Women are less likely to cycle and more likely to find transportation unaffordable than men. Non-binary individuals face the sharpest barriers: lower vehicle access, higher transit reliance, and transport costs and healthcare access gaps that far exceed those reported by women and men.
	</p>

</div>



<StatCardGrid maxCols={2}>

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
				Notably, women reported never biking to work even when they own at least one bike and have previously used bikeshare at a rate 15 percentage points higher than men and 19 percentage points higher than non-binary individuals. This suggests the barrier is not simply one of access. Perceived safety concerns, social norms and caregiving responsibilities appear to play a significant role, consistent with existing research on gendered experiences of cycling.
			</p>
		"
	/>

	<StatCardBars
		icon={iconBuilding}
		context="Transport barriers limit access to employment and healthcare, especially for non-binary individuals"
		groups={[
			{
				label: "Declined employment opportunities due to transport situation (%)",
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
		sharedLabel="Percent of respondents with access to a private vehicle"
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


<!-- <div class="text">

	<p>
		Non-binary individuals reported nearly 19 percentage points lower private vehicle ownership than both men and women. In contrast, they reported higher transit pass ownership- about 13 percentage points higher than men and 15 percentage points higher than women. They also experienced a mismatch between their frequent and preferred travel modes at a noticeably higher rate (nearly 25%).
	</p>
	<p>
		Similar patterns were observed in commuting behaviour. The share of individuals who drive to work at least once a week is nearly 22 percentage points lower than among women and nearly 26 percentage points lower than among men, while the share who take transit to work at least once a week is nearly 15 percentage points higher than among women and over 12 percentage points higher than among men. Cycling to work at least once a week was more common among individuals in the 'Non-binary' category (over one-fourth) and men (about one-fifth) than among women (just over one-tenth). Along that line, women also reported never biking to work even when they have at least one bike and used bikeshare previously at a noticeably higher rate- 15 percentage points higher than men and 19 percentage points higher than those in 'Non-binary' gender category. This finding is consistent with previous studies on gendered experiences of cycling (Ravensbergen, 2022).
	</p>
	<p>
		The share of individuals who have taken paratransit to work at least once a week is nearly 15 percentage points lower among 'Non-binary' gender category than both men and women. The share of individuals who never drive to work was higher among those in the 'Non-binary' gender category- about 16 percentage points higher than women and 20 percentage points higher than men.
	</p>
	<p>
		Overall, the findings indicate that non-binary individuals rely more on active and public transportation and less on driving for commuting purposes. Women and men, by comparison, exhibit broadly similar travel behaviour patterns, except for significantly lower cycling rates among women.
	</p>
	<p>
		Unlike commuting patterns, gender differences among men and women are more pronounced for travel to school, with men walking or biking at least a week about 9 percentage points more than women. Men also reported travelling to school as a car passenger at least once a week about 14 percentage points more than women, and using transit nearly 22 percentage points more. Similarly, the share of men using a combination of bike and ride to school at least once a week was 19 percentage points higher than women. Men also used taxi or ride hailing at a rate 12 percentage points higher than women.
	</p>
	<p>
		Non-binary individuals bike to school at considerably higher rates than both men and women- nearly 29 percentage points higher than women and 20 percentage points higher than men. They report driving to school about 7 percentage points more than women but travelling as a car passenger 8 percentage points less than women and nearly 23 percentage points less than men. They also use public transit more regularly than women (9 percentage points higher) but less regularly than men (12 percentage points lower). Non-binary individuals report using paratransit to travel to school at least once a week at rates about 50 percentage points higher than women and 49 percentage points higher than men, representing one of the largest differences across groups.
	</p>
	<p>
		More women reported never walking to school- about 8 percentage points higher than men and 31 percentage points higher than individuals in the 'Non-binary' category. However, women also reported walking to school four times a week at rates about 8 percentage points higher than men and 12 percentage points higher than those in the 'Non-binary' category. A similar pattern is observed for car travel to school. While a higher share of women than men and individuals in the 'Non-binary' category reported never driving to school or travelling as a car passenger, women also reported driving to school or travelling as a car passenger three, four or five times a week at higher rates than both men and those in the 'Non-binary' category (by about 4 to 8 percentage points). This pattern suggests that women who walk or travel by car to school are more likely to do so more consistently than men and individuals in the 'Non-binary' category. A similar pattern of consistency is observed for public transit and park-and-ride travel to school among women compared with those in the 'Non-binary' category.
	</p>


</div> -->

<!-- <Footnotes {footnotes} /> -->