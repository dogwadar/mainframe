<script>
	import Mobile from '../../components/kauhaut/Mobile.svelte';
	import Heading from '../../components/kauhaut/Heading.svelte';
	import Train from '../../components/kauhaut/Train.svelte';
	import Marquee from '../../components/kauhaut/Marquee.svelte';
	import Terminal from '../../components/kauhaut/Terminal.svelte';
	import Info from '../../components/kauhaut/Info.svelte';

	import Skyline from '../../components/kauhaut/Skyline.svelte';
	import Newspaper from '../../components/kauhaut/Newspaper.svelte';
	import Switch from '../../components/kauhaut/Switch.svelte';

	import { writable } from 'svelte/store';
	import { onMount } from 'svelte';

	export function createMediaQueryStore(query) {
		const matches = writable(false);

		onMount(() => {
			const mediaQueryList = window.matchMedia(query);
			const updateMatches = () => matches.set(mediaQueryList.matches);

			updateMatches();
			mediaQueryList.addEventListener('change', updateMatches);

			return () => mediaQueryList.removeEventListener('change', updateMatches);
		});

		return matches;
	}

	const isMobile = createMediaQueryStore('(max-width: 640px)');

	let isToggled = true;

	const handleSwitchChange = (newState) => {
		console.log(newState);
		isToggled = newState;
	};
</script>

{#if $isMobile}
	<Mobile />
{:else}
	<div class="fixed right-0 bottom-0 pr-5 pb-5">
		<Switch bind:checked={isToggled} onChange={handleSwitchChange} />
	</div>
	<main class="py-5">
		<div id="station" class="mb-20 flex flex-col items-center">
			<Heading />
			<Train />
			<Marquee />
			<Terminal />
			<Info />
		</div>
		<div id="newspaper" class="mb-20 flex flex-col items-center pt-20">
			{#if isToggled}
				<Skyline />
				<Newspaper />
			{/if}
		</div>
		<div id="home" class="pt-20"></div>
	</main>
{/if}

<style>
	main {
		background-image: linear-gradient(to top, #f3e7e9 0%, #e3eeff 99%, #e3eeff 100%);
	}
</style>
