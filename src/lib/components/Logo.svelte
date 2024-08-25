<script>
	import logo from '$lib/images/logo-w-text.svg';

	export let size = '';

	const lgClass = 'w-[400px]';
	const smClass = 'w-4';

	$: chosenSizeClass = size == 'lg' ? lgClass : smClass;

	$: totalElClass = `${chosenSizeClass} h-auto`;
</script>

<img src={logo} alt="Aaron Crockett" class={totalElClass} />
