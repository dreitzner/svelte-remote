<script lang="ts">
</script>

<svelte:head>
	<title>Choose: 🔴 or 🔵</title>
</svelte:head>

<h1>Build with svelte kit.</h1>
<h2>Choose:</h2>

<a class="bg-red" href="/remote" preload="true">Remote 📢</a>
<a class="bg-blue" href="/receiver" preload="true">Receiver 📡</a>

<style>
	a {
		padding: 0.5em 2em;
		text-decoration: none;
		color: #fff;
		border-radius: 0.2em;
	}

	.bg-red {
		background: red;
	}
	.bg-blue {
		background: blue;
	}

	:global(h1) {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4rem;
		font-weight: 100;
		line-height: 1.1;
		margin: 4rem auto;
		max-width: 14rem;
	}

	@media (min-width: 480px) {
		:global(h1) {
			max-width: none;
		}
	}
</style>
