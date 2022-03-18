<script>
	import '../app.css';
	import Header from '$lib/Header.svelte';
</script>

<div class="min-h-screen" data-theme="emerald">
	<Header />

	<main>
		<slot />
	</main>

	<footer class="p-2 footer text-base-100 footer-center">
		
	</footer>
	<!--
	<footer class="flex flex-col justify-center items-center p-5">
		<i>Created by Joseph Moussa</i>
	</footer>
	-->
</div>

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		box-sizing: border-box;
	}
</style>