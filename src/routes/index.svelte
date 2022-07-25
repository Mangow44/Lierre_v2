<script>
	import Logo from '$lib/Logo/index.svelte';
	import FullScreenSliding from '$lib/Effects/FullScreenSliding/index.svelte';
	import { indexBands } from '$lib/data/index/indexBands';

	// Attention pour accéder à static ne pas oublier le '/' devant

	// faire une flèche qui pointe vers le bas
	// faire une "scroll bar" qui montre l'avancement dans le site : body.height / current pos un truc comme ça
</script>

<main class="scrollable">
	<div id="home" class="page-container" style="background-color: #0f6466;">
		<Logo />
		<FullScreenSliding bands={indexBands} animation={true} />
	</div>

	<div id="galerie" class="page-container" style="background-color: blue;">galerie</div>

	<div id="projets" class="page-container" style="background-color: green;">projets</div>

	<div id="apropos" class="page-container" style="background-color: red;">a propos</div>

	<div id="contact" class="page-container" style="background-color: yellow;">contact</div>
</main>

<style>
	.page-container {
		position: relative;
		overflow: hidden;

		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;

		height: 100vh;
		width: 100%;
	}
</style>
