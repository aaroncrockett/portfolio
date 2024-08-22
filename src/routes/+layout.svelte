<script>
	import Header from './Header.svelte';
	import '../app.css';
</script>

<div class="app">
	<Header />
	<h1 class="text-3xl font-bold underline">Hello world!</h1>

	<main>
		<slot />
	</main>

	<footer>
		<p>&copy; 2024. Aaron Crockett.</p>
	</footer>
</div>
