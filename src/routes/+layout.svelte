<script>
	import Header from './Header.svelte';
	import '../app.css';

	let hasScrolledEnough = false;

	let elMain;

	let type = 'intro';

	function handleScroll(event) {
		const viewportHeight = window.innerHeight;
		const scrollY = window.scrollY;

		// Scroll down by one viewport height
		if (scrollY > 25 && !hasScrolledEnough) {
			hasScrolledEnough = true;
			window.scrollBy({
				top: viewportHeight,
				behavior: 'smooth' // Smooth scroll effect
			});
			type = 'main';
		}
	}
</script>

<div class="h-full app">
	<Header {type} />

	<main bind:this={elMain}>
		<slot />
	</main>

	<footer>
		<p>&copy; 2024. Aaron Crockett.</p>
	</footer>
</div>
<svelte:window on:scroll={handleScroll} />
