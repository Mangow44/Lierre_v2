<script>
	/**
	 * bands : un tableau contenant le nombre de bandes et leur délai
	 * direction : left - transition / animation vers la gauche
	 * right - transition / animation vers la droite
	 * animation : true - joue une animation
	 * transition : mettre la condition (true / false)
	 * delay : ajouter du délai à la transition / animation
	 * backgroundColor : couleur du fond
	 * zIndex : portée de la visibilitée
	 *
	 * La différence, l'animation ne se joue qu'une fois.
	 * La transition se joue et peut reprendre son état initial si la condition = false
	 */
	export let bands = [];
	export let direction = 'left';
	export let animation = false;
	export let transition = false;
	export let delay = 1;
	export let backgroundColor = '#d8b08c';
	export let zIndex = 1;
	export let id = 'undefined';
</script>

<div
	{id}
	class="full-screen-sliding 
		{transition ? 'transition' : ''}"
>
	{#each bands as band, i}
		<span
			class="band 
				{direction == 'left' ? 'translate-to-left' : ''}
				{direction == 'right' ? 'translate-to-right' : ''}
				{animation ? 'animation' : ''}"
			style="height: {100 / bands.length}vh;
				top: {i * (100 / bands.length)}vh;
				animation-delay: {delay + band}s;
				transition: {delay + band}s;
				background-color: {backgroundColor};
				z-index: {zIndex};"
		/>
	{/each}
</div>

<style>
	.band {
		position: absolute;
		left: 0;

		width: 100%;
	}

	.translate-to-left {
		transform: translateX(100%);
	}

	.translate-to-right {
		transform: translateX(-100%);
	}

	.animation {
		animation: band-sliding 0.5s ease forwards;
	}

	.transition {
		transform: translateX(0);
	}

	@keyframes band-sliding {
		100% {
			transform: translateX(0);
		}
	}
</style>
