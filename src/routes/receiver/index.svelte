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

<h1>Receiver 📡</h1>

{#if signal}
	<h2 out:fade>
		{signal}
	</h2>
{/if}

<style>
</style>
