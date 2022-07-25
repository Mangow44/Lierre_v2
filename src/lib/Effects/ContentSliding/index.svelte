<script>
	/**
	 * height : hauteur de la bande
	 * top : position absolue en haut
	 * left : position absolue à gauche
	 * transition : mettre la condition (true / false)
	 * duration : durée de la transition
	 * backgroundColor : couleur du fond
	 * color : couleur de la police
	 */
	export let height = '20vh';
	export let top = '0';
	export let left = '0';
	export let transition = false;
	export let duration = 1;
	export let backgroundColor = 'black';
	export let color = 'white';
</script>

<div
	class="translation-container {transition ? 'transition' : ''}"
	style="height: {height};
        top: {top};
        left: {left};
		transition: all {duration}s ease;
        background-color: {backgroundColor};
        color: {color};"
>
	<slot />
</div>

<style>
	.translation-container {
		z-index: 4;

		position: absolute;
		top: 0;
		left: 0;

		width: 100%;

		transform: translateX(-100%);
	}

	.transition {
		transform: translateX(0);
	}
</style>
