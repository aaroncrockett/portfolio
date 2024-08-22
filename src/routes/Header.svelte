<script>
	import { page } from '$app/stores';
	import Logo from '$lib/components/Logo.svelte';
	import Nav from '$lib/components/Nav.svelte';
	import PreNav from '$lib/components/PreNav.svelte';
	// import github from '$lib/images/github.svg';

	export let type = $page.route.id === '/' ? 'intro' : '';
</script>

<header>
	<PreNav />
	<a href="/">
		<Logo size={type === 'intro' ? 'lg' : 'sm'} />
	</a>
	<Nav {type} />
</header>
