<script>
	import { page } from '$app/stores';
	import Logo from '$lib/components/Logo.svelte';
	import Nav from '$lib/components/Nav.svelte';
	import PreNav from '$lib/components/PreNav.svelte';
	// import github from '$lib/images/github.svg';

	export let type = $page.route.id === '/' ? 'intro' : '';

	const introHeaderClass = 'bg-pink h-screen flex flex-col';
	const otherHeaderClass = 'bg-white h-auto';

	$: headerClass = type === 'intro' ? introHeaderClass : otherHeaderClass;
</script>

<header class={headerClass}>
	<div class="w-full mx-auto bg-black">
		<PreNav />
	</div>
	<div class="flex flex-col justify-between flex-1">
		<div class="relative h-full">
			<div
				class="absolute -top-[25%] left-0 right-0 w-3/4 h-[150%] mx-auto rotate-45 bg-black"
			></div>
			<div class="relative z-10 flex w-1/2 p-8 mx-auto">
				<div>
					<a href="/">
						<Logo size={type === 'intro' ? 'lg' : 'sm'} />
					</a>

					<h1 class="uppercase text-pink">Aaron Crockett</h1>
					<h2 class="text-white">
						<span>Artist.</span><span>Designer.</span><span>Engineer.</span>
					</h2>
				</div>
				<enhanced:img
					src="../lib/images/ac-profile-pic.jpeg?w=300;250"
					sizes="(min-width:1080px) 300px, (min-width:768px) 250px"
					alt="Handsome artist Aaron Crockett"
				/>
			</div>
		</div>

		<Nav {type} />
	</div>
</header>
