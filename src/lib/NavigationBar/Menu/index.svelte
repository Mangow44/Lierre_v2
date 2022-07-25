<script>
	import FullScreenSliding from '$lib/Effects/FullScreenSliding/index.svelte';
	import ContentSliding from '$lib/Effects/ContentSliding/index.svelte';
	import { menuContent } from '$lib/data/menu/menuContent';
	import { menuBands, menuDelay } from '$lib/data/menu/menuBands';
	import { burgerDelay } from '$lib/data/menu/burgerDelay';
	import { goto } from '$app/navigation';

	export let slideMenu = false;
	let displayMenu = false;

	/**
	 * Lorsque l'animation commence on affiche le menu
	 * Lorsque l'animation est terminée on cache le menu
	 */
	$: if (slideMenu) displayMenu = true;
	$: if (!slideMenu) setTimeout(() => (displayMenu = false), burgerDelay);
</script>

<div class="menu-container {displayMenu ? '' : 'hide-menu'}">
	<FullScreenSliding
		bands={menuBands}
		direction={'right'}
		transition={slideMenu}
		delay={menuDelay}
		backgroundColor={'black'}
	/>

	<div class="content-sliding">
		{#each menuContent as content, i}
			<ContentSliding
				height={100 / menuContent.length + 'vh'}
				top={i * (100 / menuContent.length) + 'vh'}
				left={'0'}
				transition={slideMenu}
				duration={menuDelay + menuBands[i]}
			>
				<div
					class="div-centered"
					on:click={() => {
						goto(`#${content.id}`);
						slideMenu = false;
					}}
				>
					{@html content.html}
				</div>
			</ContentSliding>
		{/each}
	</div>
</div>

<style>
	/* Fixed pour que le menu puisse apparaître peu importe où l'on se situe */
	.menu-container {
		z-index: 10;

		position: fixed;
		top: 0;
		left: 0;

		height: 100vh;
		width: 100%;
	}

	.hide-menu {
		z-index: -1;
	}

	.div-centered :global(.copyright) {
		font-size: 15px;
	}

	.div-centered :global(.btn) {
		height: 100%;
		width: 100%;

		text-transform: uppercase;
		font-size: 22px;

		color: white;
		background: none;
		border: none;

		cursor: pointer;

		transition: all 1s ease;
	}

	.div-centered :global(.btn:hover) {
		transform: scale(1.25);
	}
</style>
