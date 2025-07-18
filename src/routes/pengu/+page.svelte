<script>
	import { base } from '$app/paths';

	let password = '';
	let unlocked = false;
	const correctPassword = 'friend'; // found it :)

	function checkPassword() {
		if (password === correctPassword) {
			unlocked = true;
		} else {
			alert('Not it');
		}
	}
</script>

<img src="{base}/pengu.jpg" alt="my only friend" />
<article class="text-white">
	he watches me work, he watches me sleep <br />
	the allroom is where he lives <br />
	he does not speak, he does not cry and he never judges <br />
	the guardian of my sanity <br />
	a friend forever
</article>

{#if unlocked}
	<h1 class="text-white">he will protect you too</h1>
{:else}
	<div class="items-center gap-4 text-white">
		<input
			type="text"
			bind:value={password}
			placeholder="Enter the magic word..."
			class="border p-2"
		/>
		<button on:click={checkPassword} class="px-4 py-2 text-white hover:cursor-crosshair">
			Unlock
		</button>
	</div>
{/if}
