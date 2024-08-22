<script>
	import { page } from '$app/stores';
	import logo from '$lib/images/logo-me.svg';
	import github from '$lib/images/github.svg';
</script>

<header>
	<a href="/">
		<img src={logo} alt="Aaron Crockett" />
	</a>
	<nav>
		<ul>
			<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Home</a>
			</li>
			<li aria-current={$page.url.pathname === '/images' ? 'page' : undefined}>
				<a href="/about">About</a>
			</li>
			<li aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">About</a>
			</li>
		</ul>
	</nav>
</header>
