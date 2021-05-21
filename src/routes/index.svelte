<script lang="ts">
	import { onMount } from 'svelte';

	let inverted = false;

	let counter = 0;

	const onClick = () => {
		inverted = !inverted;

		counter += 1;
	};

	onMount(() => {
		const interval = setInterval(onClick, 1000);

		return () => clearInterval(interval);
	});
</script>

<svelte:head>
	<title>Lollio</title>
</svelte:head>

<div>Count: {counter}</div>

<div class="container mx-auto mt-96 select-none" on:click={onClick}>
	<h1 class="text-9xl font-heading text-center text-gray-700 cursor-pointer">
		Welcome to <span
			class="font-bold text-indigo-500 transition-all duration-1000"
			class:text-pink-500={inverted}>Lollio</span
		>
	</h1>
</div>
