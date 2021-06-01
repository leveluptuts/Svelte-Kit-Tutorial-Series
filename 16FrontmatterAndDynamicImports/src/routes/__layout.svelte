<script>
	import Header from '$lib/header.svelte';
	import '../tailwind.css';
</script>

<Header />

<main class="bg-blue-400">
	<slot />
</main>

<footer>Copywrite 2021</footer>

<!-- Svelte CSS is Scoped by default -->
<!-- <style>
	:global(header) {
		background: red;
	}
</style> -->
