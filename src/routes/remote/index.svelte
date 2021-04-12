<script lang="ts">
	const signals: string[] = ['Slide 1', 'Slide 2', 'Slide 3', 'End', 'another signal'];

	const setSignal = (signal: string): void => localStorage.setItem('signal', signal);
</script>

<svelte:head>
	<title>🔴 Remote 📢</title>
</svelte:head>
<h1>Remote 📢</h1>
{#each signals as signal}
	<button on:click={() => setSignal(signal)}>
		Set '{signal}'
	</button>
{/each}

<style>
	button {
		margin: 0.5rem;
		padding: 0.5em 2em;
		color: #fff;
		border-radius: 0.2em;
		background: red;
		border: none;
	}

	button:nth-child(even) {
		background: blue;
	}
</style>
