<script>
	export let type = '';
	import { page } from '$app/stores';
</script>

<nav>
	<ul>
		{#if type !== 'intro'}
			<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Home</a>
			</li>
		{/if}
		<li aria-current={$page.url.pathname === '/images' ? 'page' : undefined}>
			<a href="/images">images</a>
		</li>
		<li aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
			<a href="/about">About</a>
		</li>
	</ul>
</nav>
