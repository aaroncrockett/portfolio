<script>
	export let type = '';
	import { page } from '$app/stores';
</script>

<nav>
	<ul class="flex space-x-4">
		{#if type !== 'intro'}
			<li class="text-white" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Home</a>
			</li>
		{/if}
		<li class="text-white" aria-current={$page.url.pathname === '/images' ? 'page' : undefined}>
			<a href="/images">Images</a>
		</li>
		<li class="text-white" aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
			<a href="/about">About</a>
		</li>
	</ul>
</nav>
