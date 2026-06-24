
<Password/>



<script>

	import "../../../assets/global-styles.css";
	import StatCardBars from '$lib/StatCardBars.svelte';
	import StatCardGrid from '$lib/StatCardGrid.svelte';
	import TitleText from '$lib/TitleText.svelte';
	import Password from "$lib/Password.svelte";
	import Footnotes from '$lib/Footnotes.svelte';

	import iconTrain from '../../../assets/svg-icons/train.svg?url';
	import iconCar from '../../../assets/svg-icons/directions_car.svg?url';

	const footnotes = [
		// { id: 1, text: "" },
	];

</script>




<TitleText
	subtitle="MJ National Survey"
	title="Transit Proximity"
	description="Key findings on transit proximity and transport poverty across Canada"
/>

<div class="text">

	<p>
		Transit proximity is an important dimension of transport poverty as distance to transit can shape whether people are able to use public transportation as a realistic alternative to driving, particularly for work, appointments, and social activities. The findings from the National Survey can help illuminate how proximity to transit translates to mobility perceptions.
	</p>

</div>



<StatCardGrid maxCols={2}>

	<StatCardBars
		icon={iconCar}
		context="Car reliance increases with distance from public transit"
		groups={[
			{
				label: "Reported private vehicle ownership (%), by distance from nearest transit stop",
				bars: [
					{ label: "<800 m",       value: 67 },
					{ label: "800 m–1.2 km", value: 73 },
					{ label: "1.2 km–2 km",  value: 78 },
					{ label: ">2 km",         value: 88 }
				]
			}
		]}
		colors={['var(--mjYellow)', 'var(--mjGreen)', 'var(--brandLightPurple)', 'var(--brandLightBlue)']}
		backText="
			<p>
				Individuals living closer to public transit rely more on public transit and less on private vehicles. For instance, private vehicle ownership is 21 percentage points lower among individuals living within 800 m of public transit than among those living more than 2 km away. Transit pass ownership is 38 percentage points higher among individuals living within 800 m of public transit than among those living more than 2 km away.
			</p>
			<p>
				Among individuals with a fixed workplace and access to public transit, the share who take transit to work at least once a week is 26 percentage points higher for those living within 800 m of transit and 25 percentage points higher for those living between 800 m and 1.2 km, compared with those living more than 2 km away. Similarly, while nearly 42% of respondents living within 800 m of transit reported never driving to work, only 16% of respondents living beyond 2 km reported the same.
			</p>
		"
	/>

	<StatCardBars
		icon={iconCar}
		context="Perceived forced car ownership increases with distance from transit"
		groups={[
			{
				label: "Agreed or strongly agreed that they feel forced to own a car (%), by distance from nearest transit stop",
				bars: [
					{ label: "<800 m",       value: 47 },
					{ label: "800 m–1.2 km", value: 51 },
					{ label: "1.2 km–2 km",  value: 56 },
					{ label: ">2 km",         value: 65 }
				]
			}
		]}
		colors={['var(--mjYellow)', 'var(--mjGreen)', 'var(--brandLightPurple)', 'var(--brandLightBlue)']}
		backText="
			<p>
				Perceived forced car ownership increases with distance from transit. Those who live >2 km from transit agreed or strongly agreed with the statement that they feel forced to own a car 19 percentage points higher than those who live within 800 m of transit.
			</p>
		"
	/>

	<StatCardBars
		icon={iconTrain}
		context="Living close to public transit means more travel options"
		groups={[
			{
				label: "Agreed or strongly agreed that they could reach daily activities without their most frequently used mode (%), by distance from nearest transit stop",
				bars: [
					{ label: "<800 m",       value: 53 },
					{ label: "800 m–1.2 km", value: 56 },
					{ label: "1.2 km–2 km",  value: 47 },
					{ label: ">2 km",         value: 39 }
				]
			}
		]}
		colors={['var(--mjYellow)', 'var(--mjGreen)', 'var(--brandLightPurple)', 'var(--brandLightBlue)']}
		backText="
			<p>
				Compared to the other groups, those living closest to transit (<1.2km) showed the greatest agreement that they could reach destinations if their usual mode of transportation were unavailable. This suggests that transit accessibility may increase freedom of choice and movement.
			</p>
		"
	/>

	<StatCardBars
		icon={iconTrain}
		context="Living 1.2–2 km from transit may create a hidden accessibility gap"
		groups={[
			{
				label: "Agreed or strongly agreed that it takes too long to travel to work (%), by distance from nearest transit stop",
				bars: [
					{ label: "<800 m",       value: 45 },
					{ label: "800 m–1.2 km", value: 43 },
					{ label: "1.2 km–2 km",  value: 55 },
					{ label: ">2 km",         value: 44 }
				]
			}
		]}
		colors={['var(--mjYellow)', 'var(--mjGreen)', 'var(--brandLightPurple)', 'var(--brandLightBlue)']}
		backText="
			<p>
				Interestingly, respondents living 1.2-2 km from transit reported the highest agreement with the statement that travelling to work takes too long. They also reported higher agreement with the statement that there is too much traffic congestion during peak hours. For example, their mean Likert rating was 14 points higher than that of respondents living more than 2 km away. Furthermore, their mean Likert rating was 5 points higher than that of respondents living 800 m-1.2 km from transit and 8 points higher than that of those living within 800 m, indicating stronger agreement that public transit waiting times are too long.
			</p>
			<p>
				Together, these findings suggest that individuals living 1.2-2 km from transit may fall within a 'transit catchment gap', where transit is available but not easily accessible enough to fully substitute for car travel.
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
