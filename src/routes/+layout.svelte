<script>
	import Header from './Header.svelte';
	import '../app.css';
</script>

<div class="app">
	<Header type="intro" />

	<main>
		<slot />
	</main>

	<footer>
		<p>&copy; 2024. Aaron Crockett.</p>
	</footer>
</div>
