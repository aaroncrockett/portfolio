<script>
	import logo from '$lib/images/logo-me.svg';

	export let size = '';

	const lgClass = 'w-20';
	const smClass = 'w-4';

	$: chosenSizeClass = size == 'lg' ? lgClass : smClass;

	$: totalElClass = `${chosenSizeClass} h-auto`;
</script>

<img src={logo} alt="Aaron Crockett" class={totalElClass} />
