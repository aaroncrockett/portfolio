<script>
	import { page } from '$app/stores';
	import Logo from '$lib/components/Logo.svelte';
	import Nav from '$lib/components/Nav.svelte';
	import PreNav from '$lib/components/PreNav.svelte';
	// import github from '$lib/images/github.svg';

	export let type = $page.route.id === '/' ? 'intro' : '';

	const introHeaderClass = 'bg-black h-screen flex flex-col px-4';
	const otherHeaderClass = 'bg-white h-auto';
	$: headerClass = type === 'intro' ? introHeaderClass : otherHeaderClass;
</script>

<header class={headerClass}>
	<div class="mx-auto py-4">
		<PreNav />
	</div>
	<div class="flex flex-col justify-between flex-1 py-4">
		<div>
			<a href="/">
				<Logo size={type === 'intro' ? 'lg' : 'sm'} />
			</a>
		</div>

		<Nav {type} />
	</div>
</header>
