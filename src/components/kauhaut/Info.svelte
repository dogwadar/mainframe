<script>
	import { base } from '$app/paths';
</script>

<div class="flex w-9/12 justify-evenly">
	<div class="info flex flex-wrap p-4">
		<div class="flex items-center">
			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="1.5"
				stroke="currentColor"
				class="size-8"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M10.5 19.5 3 12m0 0 7.5-7.5M3 12h18"
				/>
			</svg>
			<img src="{base}/kauhaut/escalator.png" alt="" class="h-16" />
		</div>
		<div class="ml-4 flex">
			<div class="blue mr-4 h-full w-3"></div>
			<div>
				<p class="text-xl">1-4</p>
				<p class="text-sm">Thoughts</p>
			</div>
		</div>
		<div class="flex">
			<div class="green mx-4 h-full w-3"></div>
			<div>
				<p class="text-xl">5-6</p>
				<p class="text-sm">Doubts</p>
			</div>
		</div>
		<div class="flex">
			<div class="yellow mx-4 h-full w-3"></div>
			<div>
				<p class="text-xl">7-9</p>
				<p class="text-sm">Shit I Forgot</p>
			</div>
		</div>
		<div class="flex">
			<div class="orange mx-4 h-full w-3"></div>
			<div>
				<p class="text-xl">8</p>
				<p class="text-sm">Hopes</p>
			</div>
		</div>
		<div class="flex">
			<div class="dark-blue mx-4 h-full w-3"></div>
			<div>
				<p class="text-xl">6, 9-12</p>
				<p class="text-sm">Fears</p>
			</div>
		</div>
		<div class="flex">
			<div class="light-green mx-4 h-full w-3"></div>
			<div>
				<p class="text-xl">13-99</p>
				<p class="text-sm">Dreams</p>
			</div>
		</div>
		<div class="flex">
			<div class="blue mx-4 h-full w-3"></div>
			<div>
				<p class="text-xl">42</p>
				<p class="text-sm">Suppressed</p>
			</div>
		</div>
	</div>
	<div class="info flex w-4/12 flex-wrap">
		<div class="flex w-1/3 items-center pl-4">
			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="1.5"
				stroke="currentColor"
				class="size-8"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="m4.5 4.5 15 15m0 0V8.25m0 11.25H8.25"
				/>
			</svg>
			<img src="{base}/kauhaut/toilet.png" alt="" class="h-16" />
		</div>
		<div class="flex w-1/3 items-center">
			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="1.5"
				stroke="currentColor"
				class="size-8"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M19.5 13.5 12 21m0 0-7.5-7.5M12 21V3"
				/>
			</svg>
			<img src="{base}/kauhaut/skull.png" alt="" class="h-16" />
		</div>
		<div class="escape green flex w-1/3 items-center justify-center transition-colors duration-300">
			<a href="{base}/"
				><img src="{base}/kauhaut/escape.png" alt="" class="h-16" draggable="false" /></a
			>
		</div>
	</div>
</div>

<style>
	.info {
		border: 3px solid #08060a;
		background-color: #fffefa;
	}

	.blue {
		background-color: #7a73ff;
	}

	.green {
		background-color: #55d20c;
	}

	.yellow {
		background-color: #ffe44f;
	}

	.orange {
		background-color: #ffa44f;
	}

	.dark-blue {
		background-color: #3b32fc;
	}

	.light-green {
		background-color: #afff73;
	}

	.escape:hover {
		background-color: #13a400;
		cursor: pointer;
	}
</style>
