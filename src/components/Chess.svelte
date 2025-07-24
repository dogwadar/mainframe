<script>
	import { onMount } from 'svelte';
	import { base } from '$app/paths';

	const big_tl_values = [
		['32%', '90%'],
		['71%', '62.2%'],
		['32%', '35%'],
		['-8%', '62.2%']
	];
	const small_tl_values = [
		['38%', '87.5%'],
		['78%', '46%'],
		['38%', '4.5%'],
		['-1.5%', '46%']
	];

	onMount(() => {
		const mediaQuery = window.matchMedia('(max-width: 1024px)');
		let rook = document.getElementById('rook');
		let position;

		function handleMediaQueryChange(event) {
			position = window.innerWidth < 1024 ? small_tl_values : big_tl_values;

			rook.style.top = position[0][0];
			rook.style.left = position[0][1];
		}

		mediaQuery.addEventListener('change', handleMediaQueryChange);

		rook.addEventListener('click', function () {
			const currentTop = this.style.top;
			const currentLeft = this.style.left;

			let currentIndex = position.findIndex(
				(position) => position[0] === currentTop && position[1] === currentLeft
			);

			const nextIndex = (currentIndex + 1) % position.length;

			this.style.top = position[nextIndex][0];
			this.style.left = position[nextIndex][1];
		});

		handleMediaQueryChange();
	});
</script>

<div class="relative flex w-fit justify-end">
	<img
		src="{base}/chessboard.png"
		alt="chessboard"
		class="chessboard w-96 lg:w-8/12"
		draggable="false"
	/>
	<img
		src="{base}/rook.png"
		alt=""
		id="rook"
		class="rook absolute cursor-pointer"
		draggable="false"
	/>
</div>

<style>
	.rook {
		width: 9%;
		top: -1.5%;
		left: 46%;
		transition:
			top 0.5s ease,
			left 0.5s ease;
	}
</style>
