<script>
	import { base } from '$app/paths';

	const sections = [
		{
			title: 'Books',
			description: 'A curated selection of book my recommendations.',
			items: [
				'1984 - George Orwell',
				'Sandworm - Andy Greenberg',
				'Animal Farm - George Orwell',
				'The Great Escape - Paul Brickhill',
				'The Denial of Death - Ernest Becker',
				'The Emotional Brain - Joseph LeDoux',
				"Man's Search for Meaning - Viktor Frankl",
				'Anti-Tech Revolution - Theodore Kaczynski',
				'Technological Slavery - Theodore Kaczynski',
				'No Country for Old Men - Cormac McCarthy',
				'An Outline of Psycho-Analysis - Sigmund Freud'
			]
		},
		{
			title: 'Music',
			description: 'A mix of songs I enjoy; you might discover a gem.',
			items: [
				'Far from Any Road - The Handsome Family',
				'Moonshine Got Me - Daniel Norgren',
				"Drop 'Em Out - Wheeler Walker Jr.",
				'Summersong - The Decemberists',
				'Sound & Color - Alabama Shakes',
				'The Chills - Peter Bjorn and John',
				'Short Change Hero - The Heavy',
				'Nightshift - The Commodores',
				'Gorgeous - Kanye West',
				'Fritzpleasure - alt-J',
				'Losers - Balthazar'
			]
		},
		{
			title: 'Games',
			description: 'Fav games <3',
			items: [
				'Undertale - tobyfox',
				'Metro Exodus - 4A Games',
				'Resident Evil 7 - CAPCOM',
				'DREDGE - Black Salt Games',
				'Control - Remedy Entertainment',
				'Little Nightmares - Tarsier Studios',
				'Alien: Isolation - Creative Assembly',
				'Alan Wake - Remedy Entertainment',
				'Fears to Fathom (1-5) - Rayll Studios',
				'Amnesia: The Bunker - Frictional Games',
				'Red Dead Redemption 2 - Rockstar Games'
			]
		}
	];
</script>

<div class="flex w-10/12 flex-col items-center">
	<div class="relative text-center">
		<header class="mb-5 inline-block text-5xl font-bold uppercase">Dogwater Post</header>
		<p class="subhead py-3 uppercase">Dogwater, XYZ - Tuesday October 29, 2024 - Three Articles</p>
	</div>

	<div class="content flex w-full justify-evenly py-20 text-center">
		{#each sections as { title, description, items }}
			<div class="w-1/4">
				<h1 class="text-2xl">{title}</h1>
				<p class="text-sm">{description}</p>
				<ol class="list-decimal py-5">
					{#each items as item}
						<li>{item}</li>
					{/each}
				</ol>
			</div>
		{/each}
	</div>
	<div class="divider w-11/12 border"></div>
</div>

<style>
	header,
	p,
	h1,
	li,
	section {
		font-family: 'Playfair Display', serif;
	}

	header {
		line-height: 72px;
	}

	.subhead {
		border-bottom: 2px solid #2f2f2f;
		border-top: 2px solid #2f2f2f;
	}

	.hover-effect {
		transition: transform 0.3s ease;
	}

	.hover-effect:hover {
		transform: scale(1.1);
		animation: hover-grow;
	}
</style>
