<script>
	import Burger from '$lib/NavigationBar/Burger/index.svelte';
	import Menu from '$lib/NavigationBar/Menu/index.svelte';

	let slideMenu = false;
</script>

<div class="navbar-container">
	<Burger bind:slideMenu />
</div>
<Menu bind:slideMenu />

<style>
	.navbar-container {
		z-index: 20;

		position: fixed;
		top: 1rem;
		right: 1rem;

		height: 4rem;
		width: auto;

		mix-blend-mode: exclusion;
	}
</style>
