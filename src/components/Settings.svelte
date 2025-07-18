<script>
	import { base } from '$app/paths';
	import { onMount } from 'svelte';

	let audio;
	let isPlaying = false;

	onMount(() => {
		audio = new Audio(`${base}/music.mp3`);
		audio.loop = true;
		audio.volume = 0.2;

		const start = () => {
			audio.play().catch(console.warn);
			window.removeEventListener('click', start);
		};
	});

	function toggleAudio() {
		if (!audio) return;

		if (isPlaying) {
			audio.pause();
		} else {
			audio.play().catch(console.warn);
		}
		isPlaying = !isPlaying;
	}
</script>

<div class="relative flex w-full justify-end gap-5 pt-5 pr-5">
	<img
		id="play"
		src="{base}/play.jpg"
		alt="Play/Stop Button"
		class="w-8 cursor-crosshair"
		on:click={toggleAudio}
	/>

	<a href="{base}/todo"
		><img src="{base}/important.png" alt="important" class="h-8 w-8 cursor-crosshair" /></a
	>
</div>
