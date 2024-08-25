<script>
	import { fade, fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	import { page } from '$app/stores';
	import { quintOut } from 'svelte/easing';
	import introLogo from '$lib/images/logo-w-text.svg';
	import Nav from '$lib/components/Nav.svelte';

	export let type = $page.route.id === '/' ? 'intro' : '';

	const defaultHeaderClass = 'flex flex-col h-full transition';

	$: headerClass =
		type === 'intro' ? 'bg-pink ' + defaultHeaderClass : 'bg-black ' + defaultHeaderClass;

	const defaultBackgroundClass =
		'transition absolute top-0 left-0 right-0 w-full mx-auto bg-black md:w-4/5 ';

	const introBackgroundClass = 'rotate-45 h-full lg:h-screen xl:h-[135%]';

	$: backgroundClass =
		type === 'intro'
			? `${introBackgroundClass} ${defaultBackgroundClass}`
			: defaultBackgroundClass + 'h-full';

	let pageLoaded = false;

	onMount(async () => {
		pageLoaded = true;
	});
</script>

<header class={headerClass}>
	<Nav {type} />
	{#if pageLoaded}
		<div
			class="relative h-screen"
			out:fade={{
				duration: 400,
				delay: 100,
				easing: quintOut
			}}
		>
			<div
				transition:fly={{
					delay: 300,
					duration: 750,
					x: 0,
					y: '-100%',
					easing: quintOut,
					opacity: 0.2
				}}
				class={backgroundClass}
			></div>

			<div
				class="relative z-10 flex items-center justify-center h-full p-8 mx-auto space-x-8 md:w-2/3"
				transition:fly={{
					delay: 500,
					duration: 750,
					x: '-200%',
					y: 0,
					easing: quintOut,
					opacity: 0.1
				}}
			>
				<div class="flex items-end md:space-x-6">
					<img src={introLogo} alt="Aaron Crockett" class="h-auto w-[400px]" />

					<enhanced:img
						src="../lib/images/ac-profile-pic.jpeg?w=250;150"
						sizes="(min-width:1080px) 250px,  150px"
						alt="Handsome artist Aaron Crockett"
						class="pb-[9px] md:block hidden"
					/>
				</div>
			</div>
		</div>
	{/if}
</header>
