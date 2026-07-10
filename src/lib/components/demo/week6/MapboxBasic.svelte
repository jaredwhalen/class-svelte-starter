<script>
	import { onMount } from 'svelte';
	import mapboxgl from 'mapbox-gl';
	import 'mapbox-gl/dist/mapbox-gl.css';
	import MapboxKeyMissing from './MapboxKeyMissing.svelte';

	const token = import.meta.env.DEV
		? (import.meta.env.DEV_MAPBOX_ACCESS_TOKEN ?? '')
		: (import.meta.env.PROD_MAPBOX_ACCESS_TOKEN ?? '');
	const hasToken = Boolean(token.trim());

	const center = [-73.9626, 40.8075];
	const zoom = 14;
	const label = 'Columbia University';
	const color = '#b31b1b';

	let container = $state();
	/** @type {mapboxgl.Map | undefined} */
	let map;

	onMount(() => {
		if (!hasToken || !container) return;

		mapboxgl.accessToken = token;

		map = new mapboxgl.Map({
			container,
			style: 'mapbox://styles/mapbox/light-v11',
			center,
			zoom
		});

		map.addControl(new mapboxgl.NavigationControl(), 'top-right');

		new mapboxgl.Marker({ color })
			.setLngLat(center)
			.setPopup(
				new mapboxgl.Popup({ offset: 28, closeButton: false, closeOnClick: false }).setHTML(
					`<strong>${label}</strong>`
				)
			)
			.addTo(map)
			.togglePopup();

		return () => map?.remove();
	});
</script>

{#if hasToken}
	<div bind:this={container} class="map"></div>
{:else}
	<MapboxKeyMissing />
{/if}

<style>
	.map {
		width: 100%;
		height: 24rem;
		border-radius: 0.35rem;
		overflow: hidden;
	}
</style>
