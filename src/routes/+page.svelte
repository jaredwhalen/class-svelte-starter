<script>
	import * as d3 from 'd3';
	import states from '$lib/data/us-states.json';
	import incomeData from '$lib/data/state-median-income.json';

	const parsePercent = (value) => Number(value.replace('%', ''));

	const growthByState = new Map(
		incomeData.map((row) => [row.State, parsePercent(row['Growth rate'])])
	);
	const growthRates = incomeData.map((row) => parsePercent(row['Growth rate']));

	let width = $derived(0);
	let height = 600;

	let projection = $derived(d3.geoAlbersUsa().fitSize([width, height], states));
	let path = $derived(d3.geoPath(projection));

	let colorScale = $derived(
		d3.scaleQuantize().domain(d3.extent(growthRates)).range(d3.schemeBlues[7])
	);

	let columbia = $derived(projection([-73.96293748043828, 40.80782378612709]));
</script>

<div bind:clientWidth={width}>
	<svg viewBox="0 0 {width} {height}" {width} {height}>
		{#each states.features as feature}
			{@const growth = growthByState.get(feature.properties.NAME)}
			<path
				d={path(feature)}
				stroke="white"
				fill={growth != null ? colorScale(growth) : '#ddd'}
			/>
		{/each}

		{#if columbia}
			<circle cx={columbia[0]} cy={columbia[1]} r={4} stroke="white" fill="#000"></circle>

			<text x={columbia[0]} y={columbia[1]} text-anchor="middle">😊</text>
		{/if}
	</svg>
</div>
