<script lang="ts">
	import { fade } from 'svelte/transition';
	const storageKey = 'signal';
	let signal = '';
	let timeout;
	const listener = () => {
		const value = localStorage.getItem(storageKey);
		if (!value) return;

		if (timeout) clearTimeout(timeout);

		signal = value;
		localStorage.removeItem(storageKey);
		timeout = setTimeout(() => {
			signal = '';
		}, 3000);
	};
</script>

<svelte:head>
	<title>🔵 Receiver 📡</title>
</svelte:head>

<svelte:window on:storage={listener} />

{#if signal}
	<h1 out:fade>
		{signal}
	</h1>
{/if}

<style>
	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4rem;
		font-weight: 100;
		line-height: 1.1;
		margin: 4rem auto;
		max-width: 14rem;
	}

	@media (min-width: 480px) {
		h1 {
			max-width: none;
		}
	}
</style>
