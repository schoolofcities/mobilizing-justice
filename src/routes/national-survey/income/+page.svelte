<script>

	import "../../../assets/global-styles.css";
	import StatCardComparison from '$lib/StatCardComparison.svelte';
	import StatCardBars from '$lib/StatCardBars.svelte';
	import StatCardGrid from '$lib/StatCardGrid.svelte';
	import TitleText from '$lib/TitleText.svelte';
	import AuthorDate from '$lib/AuthorDate.svelte';
	import Footnote from '$lib/Footnote.svelte';
	import Footnotes from '$lib/Footnotes.svelte';

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



<StatCardGrid maxCols={2}>

	<StatCardComparison
		context="Low income households are far less likely to own private vehicles"
		stat1="31%"
		color1="var(--mjYellow)"
		label1="of low income households do not own a private vehicle"
		stat2="3%"
		color2="var(--mjGreen)"
		label2="of high income households do not own a private vehicle"
		description="Low income households are those that make less than $50,000 before tax (n = 200). High income households are those that make more than $200,000 before tax (n = 320)."
	/>

	<StatCardBars
		context="Low income households are more likely to use public transit"
		groups={[
			{
				label: "Take public transit to work 5× per week (%)",
				bars: [
					{ label: "Individuals in low income households", value: 22 },
					{ label: "Individuals in high income households", value: 11 }
				]
			},
			{
				label: "Transit pass ownership (%)",
				bars: [
					{ label: "Individuals in low income households", value: 12 },
					{ label: "Individuals in high income households", value: 5 }
				]
			}
		]}
		description="Low income households are those that make less than $50,000 before tax (n = 200). High income households are those that make more than $200,000 before tax (n = 320)."
	/>

	<StatCardBars
		context="Low income households make use of active travel more"
		groups={[
			{
				label: "Walk to work 5× per week (%)",
				bars: [
					{ label: "Individuals in low income households", value: 30 },
					{ label: "Individuals in high income households", value: 24 }
				]
			}
		]}
		description="Low income households are those that make less than $50,000 before tax (n = 200). High income households are those that make more than $200,000 before tax (n = 320)."
	/>

	<StatCardComparison
		context="Do transport constraints lead to a decline employment opportunities?"
		stat1="53%"
		color1="var(--mjYellow)"
		label1="of low income households agreed or strongly agreed with this statement"
		stat2="40%"
		color2="var(--mjGreen)"
		label2="of high income households agreed or strongly agreed with this statement"
		description="Low income households are those that make less than $50,000 before tax (n = 200). High income households are those that make more than $200,000 before tax (n = 320)."
	/>

</StatCardGrid>


<div class="text">

	<AuthorDate
		date="May 2026"
		credits={[
			{ role: "Research", names: "Author names" },
			{ role: "Writing", names: "Author names" },
			{ role: "Graphics", names: "Author names" }
		]}
	/>

	<h2>
		Driving, transit, and active travel
	</h2>
	<p>
		Low-income individuals reported lower car ownership and higher transit pass ownership compared to middle- and high-income individuals. For instance, fewer than 3% of high-income individuals reported not owning any private vehicles, compared with 31% of low-income individuals. Conversely, the share of low-income individuals possessing transit passes is 7 percentage points higher than that of high-income individuals. Consequently, low-income individuals reported walking and taking public transit to work more than middle- and high-income individuals. For instance, the share of low-income respondents taking public transit to work five times a week is 11 percentage points higher than that of high-income respondents. They also reported driving less than the other two income groups. 
	</p>
	<p>
		There are modest differences among income groups in the use of active transportation to work. The gap between high- and low-income individuals who never walk or bike to work is approximately 10 and 7 percentage points, respectively. Similarly, the gap between middle- and low-income individuals who never walk or bike to work is approximately 8 and 6 percentage points, respectively. The share of individuals who walk to work five times per week is nearly 6 percentage points higher among low-income individuals than among high-income individuals. Overall, the findings indicate that low-income individuals use active transportation for commuting at slightly higher rates than middle- and high-income groups, which is consistent with previous literature<Footnote id={[1, footnotes[0].text]} /><Footnote id={[2, footnotes[1].text]} />
	</p>
	<p>
		Fewer low-income individuals reported never using a taxi or ride-hailing to work, nearly 6 percentage points lower than the other two income groups. This may be attributed to lower car ownership among low-income populations, as noted before, and reliance on public transit, which can be unreliable at times, or active transportation, which might be inconvenient during adverse weather conditions. The use of taxis or ride-hailing services among individuals living in transport poverty conditions has been reported in previous MJ research as well<Footnote id={[3, footnotes[2].text]} />. 
	</p>

	<h2>
		Barriers to participation
	</h2>
	<p>
		Low-income respondents showed higher agreement that transport constraints led them to decline employment opportunities (mean Likert ratings: 43.2832.03, 35.2131.62 and 28.9329.13, respectively, for low, middle and high-income respondents), suggesting that higher income is associated with a lower likelihood of foregoing employment opportunities due to transport-related challenges. These suggest that transportation disadvantages contribute to a vicious cycle of transport-related social exclusion and socioeconomic disadvantages, particularly among low-income populations<Footnote id={[4, footnotes[3].text]} />. Similar patterns were observed for not pursuing education due to transportation barriers, suggesting the potential for longitudinal and intergenerational transport poverty, as reduced educational participation may limit access to better employment opportunities<Footnote id={[5, footnotes[4].text]} />. 
	</p>

	<p>
		Among individuals with a driver’s license and at least one car in the household, the mean Likert ratings are nearly identical among the three income groups when it comes to perceptions of forced car ownership. The proportion reporting near-ideal or neutral perceptions of forced car ownership (Likert rating 45–55) is about 5 percentage points higher among low-income individuals than among high-income individuals. Also, fewer low-income individuals reported being forced to own a car than did members of the other two income groups. These findings suggest that income may not have a straightforward relationship with perceptions of forced car ownership. Connaughton et al.<Footnote id={[6, footnotes[5].text]} /> argue that forced car ownership is a nebulous concept in Canada, making it difficult for researchers and policymakers to operationalize when the majority of North Americans live in overwhelmingly auto-dependent environments. 
	</p>

	<p>
		However, low-income individuals reported a stronger sense of being forced to rely on active and public transportation than the other two income groups, with mean Likert score differences ranging from 6 to 10. Furthermore, affordability has been reported most frequently by low-income respondents as a reason for not using their preferred mode of transport. 
	</p>

	<p>
		Interestingly, high-income individuals showed higher agreement that it takes too long to travel to work (mean Likert ratings: 41.3930.65, 44.231.38 and 50.2431.57, respectively for low, middle and high-income respondents). They also reported experiencing more traffic congestion during peak hours, with mean Likert ratings more than 6 points higher than those of low-income respondents. Several factors may explain this pattern. Low-income respondents may become accustomed to recurring transportation constraints and adjust their perceptions accordingly. In contrast, high-income individuals may have access to a larger job catchment area due to higher private vehicle ownership, leading to longer commute distances. Higher car ownership and usage may also increase the likelihood of being stuck in traffic congestion compared to individuals who bike or use rapid transit, such as subways.
	</p>

	<p>
		Low-income individuals generally showed more positive perceptions of public transit, whereas high-income individuals showed a general inclination towards driving, though the differences in mean Likert scores across income groups are small. High-income individuals found walking to be safer, more enjoyable, and more affordable than low-income individuals did. These overall positive perceptions may be driven by high-income individuals living in safer neighbourhoods and walking by choice and subconsciously comparing a walking trip to a costlier alternative, such as driving, which may involve fuel and parking expenses. Low-income individuals are more likely to walk due to compulsion (such as forced reliance on active transport, as we discussed previously) and may compare walking with subsidized transit, making the affordability advantage less obvious.
	</p>

</div>

<Footnotes {footnotes} />