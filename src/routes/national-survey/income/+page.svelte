
<!-- <Password/> -->



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

	import iconCar from '../../../assets/svg-icons/directions_car.svg?url';
	import iconTrain from '../../../assets/svg-icons/train.svg?url';
	import iconBuilding from '../../../assets/svg-icons/domain.svg?url';
	import iconWalk from '../../../assets/svg-icons/directions_walk.svg?url';
	import iconMoney from '../../../assets/svg-icons/attach_money.svg?url';
	import iconClock from '../../../assets/svg-icons/schedule.svg?url';

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
	title="Income"
	description="Key findings on income and transport poverty across Canada"
/>

<div class="text">

	<p>
		In Canada, household income shapes nearly every aspect of how people get around. What modes people can afford, how far they can realistically travel, and whether transportation opens up opportunities or closes them off all vary significantly by income.
	</p>
	<p>
		These findings come from the <a href="https://mobilizingjustice.ca/working-groups/national-survey-of-transport-poverty-and-trse/" target="_blank">Mobilizing Justice National Survey on Transport Poverty</a>. Across Canada, lower-income households face compounding disadvantages: less access to cars, affordability impacting travel choices, and  transportation barriers reducing employment opportunities.
	</p>

</div>



<StatCardGrid maxCols={2}>

	<StatCardComparison
		icon={iconCar}
		context="Low-income households are far less likely to own private vehicles"
		stat1="31%"
		color1="var(--mjYellow)"
		label1="of individuals living in low-income households do not own a private vehicle"
		stat2="3%"
		color2="var(--mjGreen)"
		label2="of individuals living in high-income households do not own a private vehicle"
		description="Low-income households are those that make less than $60,000 before tax (n = 200). High-income households are those that make more than $120,000 before tax (n = 320)."
		backText="
			<p>
				31% of low-income individuals do not own a private vehicle, compared to fewer than 3% of high-income individuals. Low-income individuals are also more likely to hold a transit pass, at a rate 7 percentage points higher than high-income individuals. Without access to a car, daily travel depends heavily on transit and active modes. As a result, low-income individuals walk and take public transit to work at considerably higher rates than middle- and high-income groups, and report driving much less.
			</p>
		"
	/>

	<StatCardBars
		icon={iconTrain}
		context="Low-income households are more likely to use public transit"
		groups={[
			{
				label: "Take public transit to work 5× per week (%)",
				bars: [
					{ label: "Individuals in low-income households", value: 22 },
					{ label: "Individuals in high-income households", value: 15 }
				]
			},
			{
				label: "Transit pass ownership (%)",
				bars: [
					{ label: "Individuals in low-income households", value: 15 },
					{ label: "Individuals in high-income households", value: 4 }
				]
			}
		]}
		description="Low-income households are those that make less than $60,000 before tax (n = 200). High-income households are those that make more than $120,000 before tax (n = 320)."
		backText="
			<p>
				22% of low-income individuals take public transit to work five times a week, compared to 15% of high-income individuals, a gap of 11 percentage points. Transit pass ownership follows the same pattern, at 15% among low-income households versus just 4% among high-income households.
			</p>
			<p>
				Interestingly, fewer low-income individuals reported never using a taxi or ride-hailing service for work trips, nearly 6 percentage points below the other income groups. This likely reflects the occasional unreliability of transit and the impracticality of walking or cycling in adverse weather, making ride-hailing a fallback option when other modes fall short, but only for residents who can afford it.
			</p>
			<p>
				Low-income individuals also generally showed more positive perceptions of public transit compared to high-income individuals, who showed a greater inclination towards driving. The differences in results is modest, but the direction is consistent.
			</p>
		"
	/>

	<StatCardTwoSquares
		icon={iconBuilding}
		context="Transport barriers are costing low-income residents job opportunities"
		sharedLabel="Percent of respondents that agreed or strongly agreed that their transport situation has led them to decline employment opportunities"
		stats={[
			{ stat: 35, color: "var(--mjYellow)", label: "of low-income respondents" },
			{ stat: 21, color: "var(--mjGreen)",  label: "of high-income respondents" }
		]}
		description="Low-income households are those that make less than $60,000 before tax (n = 200). High-income households are those that make more than $120,000 before tax (n = 320)."
		backText="
			<p>
				35% of low-income individuals agreed or strongly agreed that their transport situation has led them to decline employment opportunities, compared to 21% of high-income individuals.
			</p>
			<p>
				Similar patterns were found for education. Low-income respondents were more likely to report not pursuing education due to transport barriers. Reduced educational participation may limit access to better employment over time, suggesting transport disadvantage can compound across generations.
			</p>
			<p>
				It is also worth noting that this figure may underestimate the true impact. Low-income individuals who have grown accustomed to recurring transport constraints may no longer consciously register them as barriers, which could suppress self-reported agreement even when the underlying conditions are more limiting.
			</p>
		"
	/>

	<StatCardBars
		icon={iconWalk}
		context="Low-income residents walk and bike more frequently"
		groups={[
			{
				label: "Walk to work at least once per week (%)",
				bars: [
					{ label: "Individuals in low-income households", value: 32 },
					{ label: "Individuals in high-income households", value: 22 }
				]
			},
			{
				label: "Bike to work at least once per week (%) [PLACEHOLDER DATA]",
				bars: [
					{ label: "Individuals in low-income households", value: 7 },
					{ label: "Individuals in high-income households", value: 2 }
				]
			}
		]}
		description="Low-income households are those that make less than $60,000 before tax (n = 200). High-income households are those that make more than $120,000 before tax (n = 320)."
		backText="
			<p>
				32% of low-income individuals walk to work at least once a week, compared to 22% of high-income individuals. The share who walk to work five times per week is nearly 6 percentage points higher among low-income individuals than high-income individuals. A similar pattern holds for cycling: the share who never bike to work is around 7 to 10 percentage points lower among low-income individuals than middle- and high-income groups.
			</p>
			<p>
				For low-income individuals, this is more likely to reflect necessity than preference. High-income individuals who walk tend to compare it against driving, with its fuel and parking costs, making walking feel affordable and enjoyable. Low-income individuals are more likely to compare walking against subsidized transit, which makes that affordability advantage much less obvious.
			</p>
			<p>
				This may help explain why high-income individuals rated walking as safer, more enjoyable, and more affordable than low-income individuals did. High-income individuals tend to walk by choice in safer neighbourhoods; low-income individuals are more likely to walk out of compulsion, which shapes how they perceive the experience.
			</p>
		"
	/>

	<StatCardStack
		icon={iconMoney}
		context="Affordability is the main reason low-income individuals can't travel the way they prefer"
		sharedLabel="Percent of respondents that identified affordability as a reason they do not use their preferred mode of transport"
		stats={[
			{ stat: "17%", color: "var(--mjYellow)", label: "of low-income residents" },
			{ stat: "4%",  color: "var(--mjGreen)",  label: "of high-income residents" }
		]}
		description="Low-income households are those that make less than $60,000 before tax (n = 200). High-income households are those that make more than $120,000 before tax (n = 320)."
		backText="
			<p>
				17% of low-income individuals identified affordability as a reason they do not use their preferred mode of transport, compared to just 4% of high-income individuals. Low-income individuals also reported a stronger sense of being forced to rely on active and public transportation, with score differences of 6 to 10 points compared to other income groups.
			</p>
			<p>
				Among those who owned a vehicle, perceptions of forced car ownership were nearly identical across income groups. The proportion with near-neutral perceptions of car ownership was about 5 percentage points higher among low-income individuals than high-income individuals, suggesting the relationship between income and car ownership pressure is not straightforward.
			</p>
		"
	/>

	<StatCardStack
		icon={iconClock}
		context="Longer commutes and experiencing congestion is more common among high-income residents"
		sharedLabel="Percent of respondents that agreed or strongly agreed that it takes too long to travel to work [PLACEHOLDER DATA]"
		stats={[
			{ stat: "20%", color: "var(--mjYellow)", label: "of low-income residents" },
			{ stat: "30%", color: "var(--mjGreen)",  label: "of High-income residents" }
		]}
		description="Low-income households are those that make less than $60,000 before tax (n = 200). High-income households are those that make more than $120,000 before tax (n = 320)."
		backText="
			<p>
				High-income individuals reported longer commute times and more peak-hour congestion than low-income individuals. High-income individuals, with greater access to private vehicles, may commute from further away and have access to a larger job catchment area. Higher car use also increases exposure to traffic congestion compared to those who bike or use rapid transit.
			</p>
			<p>
				It is also possible that high-income individuals are more likely to work standard 9-to-5 schedules, placing them squarely in peak congestion periods. Low-income respondents may have adjusted their expectations around recurring transport constraints, which could suppress how they rate commute time even when objectively facing difficult conditions.
			</p>
		"
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

	<!-- <h2>
		Driving, transit, and active travel
	</h2>
	<p>
		Low-income individuals reported lower car ownership and higher transit pass ownership compared to middle- and high-income individuals. For instance, fewer than 3% of high-income individuals reported not owning any private vehicles, compared with 31% of low-income individuals. The share of low-income individuals possessing transit passes is 7 percentage points higher than that of high-income individuals.
	</p>
	<p>
		Low-income individuals reported taking public transit to work more than middle- and high-income individuals. For instance, the share of low-income respondents taking public transit to work five times a week is 11 percentage points higher than that of high-income respondents. They also reported driving less than the other two income groups.
	</p>
	<p>
		There are modest differences among income groups in the use of active transportation to work. The gap between high- and low-income individuals who never walk or bike to work is approximately 10 and 7 percentage points, respectively. Similarly, the gap between middle- and low-income individuals who never walk or bike to work is approximately 8 and 6 percentage points, respectively. The share of individuals who walk to work five times per week is nearly 6 percentage points higher among low-income individuals than among high-income individuals. Overall, the findings indicate that low-income individuals use active transportation for commuting at slightly higher rates than middle- and high-income groups, which is consistent with previous literature<Footnote id={[1, footnotes[0].text]} /><Footnote id={[2, footnotes[1].text]} />.
	</p>
	<p>
		Fewer low-income individuals reported never using a taxi or ride-hailing to work, nearly 6 percentage points lower than the other two income groups. This may be attributed to lower car ownership among low-income populations, as noted before, and reliance on public transit, which can be unreliable at times, or active transportation, which might be inconvenient during adverse weather conditions. The use of taxis or ride-hailing services among individuals living in transport poverty conditions has been reported in previous MJ research as well<Footnote id={[3, footnotes[2].text]} />.
	</p>

	<h2>
		Barriers to participation
	</h2>
	<p>
		Low-income respondents showed higher agreement that transport constraints led them to decline employment opportunities (mean Likert ratings: 43.28±32.03, 35.21±31.62 and 28.93±29.13, respectively, for low-, middle- and high-income respondents), suggesting that higher income is associated with a lower likelihood of foregoing employment opportunities due to transport-related challenges. These findings suggest that transportation disadvantages contribute to a vicious cycle of transport-related social exclusion and socioeconomic disadvantage, particularly among low-income populations<Footnote id={[4, footnotes[3].text]} />. Similar patterns were observed for not pursuing education due to transportation barriers, suggesting the potential for longitudinal and intergenerational transport poverty, as reduced educational participation may limit access to better employment opportunities<Footnote id={[5, footnotes[4].text]} />.
	</p>
	<p>
		Among individuals with a driver’s license and at least one car in the household, the mean Likert ratings are nearly identical among the three income groups when it comes to perceptions of forced car ownership. The proportion reporting near-ideal or neutral perceptions of car ownership (Likert rating 45–55) is about 5 percentage points higher among low-income individuals than among high-income individuals. Fewer low-income individuals also reported being forced to own a car than did members of the other two income groups. These findings suggest that income may not have a straightforward relationship with perceptions of forced car ownership.
	</p>
	<p>
		However, low-income individuals reported a stronger sense of being forced to rely on active and public transportation than the other two income groups, with mean Likert score differences ranging from 6 to 10. Furthermore, affordability has been reported most frequently by low-income respondents as a reason for not using the preferred mode of transport.
	</p>
	<p>
		Interestingly, high-income individuals showed higher agreement that it takes too long to travel to work (mean Likert ratings: 41.39±30.65, 44.2±31.38 and 50.24±31.57, respectively, for low-, middle- and high-income respondents). They also reported experiencing more traffic congestion during peak hours, with mean Likert ratings more than 6 points higher than those of low-income respondents. Several factors may explain this pattern. Low-income respondents may become accustomed to recurring transportation constraints and adjust their perceptions accordingly. In contrast, high-income individuals may have access to a larger job catchment area due to higher private vehicle ownership, leading to longer commute distances. Higher car ownership and usage may also increase the likelihood of being stuck in traffic compared to individuals who bike or use rapid transit, such as subways.
	</p>
	<p>
		Low-income individuals generally showed more positive perceptions of public transit, whereas high-income individuals showed a general inclination towards driving, though the differences in mean Likert scores across income groups are small. High-income individuals found walking to be safer, more enjoyable, and more affordable than low-income individuals did. These overall positive perceptions may be driven by high-income individuals living in safer neighbourhoods and walking by choice, subconsciously comparing a walking trip to a costlier alternative such as driving, which may involve fuel and parking expenses. Low-income individuals are more likely to walk due to compulsion (such as forced reliance on active transport) and may compare walking with subsidized transit, making the affordability advantage less obvious.
	</p> -->

</div>

<!-- <Footnotes {footnotes} /> -->
