<script>
	export let type = '';
	import { page } from '$app/stores';
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	import Pride from '$lib/images/new-pride-flag-01.webp';

	let pageLoaded = false;
	onMount(async () => {
		pageLoaded = true;
	});
</script>

<nav class="fixed z-10 w-full mx-auto bg-black">
	{#if pageLoaded}
		<ul
			class="relative z-10 flex items-center justify-between h-12 mx-auto md:w-3/4"
			transition:fade={{
				delay: 300,
				duration: 750,

				easing: quintOut,
				opacity: 0.2
			}}
		>
			<div class="flex space-x-4">
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
			</div>
			<div>
				<img src={Pride} alt="pride flag" width="50" />
			</div>
		</ul>
	{/if}
</nav>
