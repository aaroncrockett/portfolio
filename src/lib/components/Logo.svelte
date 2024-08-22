<script>
	import logo from '$lib/images/logo-me.svg';
	let sizeProp = 'lg';

	const lgClass = 'w-20';
	const smClass = 'w-4';

	$: chosenSizeClass = sizeProp == 'lg' ? lgClass : smClass;

	$: totalElClass = `${chosenSizeClass} h-auto`;
</script>

<img src={logo} alt="Aaron Crockett" class={totalElClass} />
