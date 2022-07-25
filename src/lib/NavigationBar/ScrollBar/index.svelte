<script>
	import { onMount } from 'svelte';

	/**
	 * Ici on actualise la position de la scrollbar
	 * Au chargement de la page - au scroll de l'utilisateur
	 *
	 * Comment on procède ?
	 * ScrollTop = nombre de pixels scroll depuis le haut de la page
	 * ScrollHeight = taille de la page
	 * ClientHeight = taille de l'écran de l'utilisateur
	 *
	 * Produit en croix après ça
	 * % ? = ScrollTop
	 * 100% = ScrollHeight - ClientHeight
	 */
	onMount(() => {
		const scrollbar = document.querySelector('.scrollbar');
		const updateScrollbarPosition = () => {
			const { scrollTop, scrollHeight, clientHeight } = document.documentElement;
			// -100 + produit en croix (car on commence avec un translate à -100%)
			let scrollbarPosition = -100 + (scrollTop * 100) / (scrollHeight - clientHeight);
			scrollbar.style.transform = `translateX(${scrollbarPosition}%)`;
		};

		updateScrollbarPosition();

		window.addEventListener('scroll', () => {
			updateScrollbarPosition();
		});
	});
</script>

<span class="scrollbar" />

<style>
	.scrollbar {
		z-index: 20;
		position: fixed;

		width: 100%;
		height: 6px;

		transition: all 0.2s ease;

		transform: translateX(-100%);

		background-color: white;
	}
</style>
