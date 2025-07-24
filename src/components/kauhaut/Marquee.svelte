<script>
	import { onMount } from 'svelte';
	import Marqueeck from '@arisbh/marqueeck';

	let currentTime = '';

	let marqueeMessage = `-------------------
	You have arrived at Dogwater Station! Enjoy your visit and remember to
	stay hydrated because hydration is essential for maintaining health, supporting physical
	and mental performance, and ensuring the body operates efficiently. Making hydration a priority
	can have a positive impact on your overall well-being. Ever heard of a successful, dehydrated
	entrepreneur? Me neither. It's not that hard either. Just get up from your chair and drink a
	big glass of juicy, rejuvenating water. Do it right now, I'll be waiting for you here ..........................................................................................................................................................................................................
	why are you still here? Please consider my advice. I promise you will feel way better after drinking
	something. I'm going to patiently wait here, but now go..........................................................................................................................................................................................................................................................................................................................................
	Listen to me you little shit, do you even understand what I am trying to do
	here for you? Probably not with that shriveled, dry brain of yours. You know what? Don't drink
	that glass of water. In fact, do not drink any more water. Ever. It would be a waste anyway.
	That's right, YOU ARE WASTE. You unthankful piece of ********** ******* of a ********************
	with a *********** as a ***************** -`;

	const updateTime = () => {
		const now = new Date();
		currentTime = now.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });
	};

	const startClock = () => {
		updateTime();
		setInterval(updateTime, 60000);
	};

	onMount(() => {
		startClock();
	});
</script>

<div
	class="marquee text-background mb-5 flex w-11/12 flex-col flex-wrap items-center rounded py-4 md:flex-row"
>
	<div class="flex flex-col p-2 text-center xl:w-1/12">
		<p class="font-bold opacity-70">タイム</p>
		<p class="time md:text-2xl">{currentTime}</p>
	</div>
	<div class="flex w-10/12 flex-col text-center md:px-20 xl:w-11/12">
		<p class="font-bold opacity-70">ニュース</p>
		<div class="flex h-full w-full items-center justify-center md:text-3xl">
			<Marqueeck options={{ direction: 'left', speed: 140 }}>
				<p class="marquee-text">{marqueeMessage}</p>
			</Marqueeck>
		</div>
	</div>
</div>

<style>
	.marquee {
		background-color: #08060a;
		overflow: hidden;
		position: relative;
	}

	.marquee-text {
		color: #55d20c;
	}

	@keyframes marquee {
		0% {
			transform: translateX(100%); /* Start from right */
		}
		100% {
			transform: translateX(-100%); /* Move to left */
		}
	}
</style>
