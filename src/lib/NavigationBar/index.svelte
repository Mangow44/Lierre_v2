<script>
	import Burger from '$lib/NavigationBar/Burger/index.svelte';
	import Menu from '$lib/NavigationBar/Menu/index.svelte';
	import ScrollBar from '$lib/NavigationBar/ScrollBar/index.svelte';

	let slideMenu = false;
</script>

<header>
	<ScrollBar />
	<Burger bind:slideMenu />
	<Menu bind:slideMenu />
</header>
