<script>
	export let slideMenu = false;
</script>

<div
	class="burger-container"
	on:click={() => {
		slideMenu = !slideMenu;
	}}
>
	<span class="line {slideMenu ? 'cross' : ''}" />
	<span class="line {slideMenu ? 'cross' : ''}" />
</div>

<style>
	.burger-container {
		z-index: 20;

		position: fixed;
		top: 1rem;
		right: 1rem;

		height: 2.6rem;
		width: 2.6rem;

		margin-right: 2rem;

		transition: all 0.5s ease;

		cursor: pointer;

		mix-blend-mode: exclusion;
	}

	.burger-container:hover {
		transform: scale(1.14);
	}

	.burger-container .line {
		position: absolute;
		height: 3px;
		width: 100%;

		transition: all 0.5s ease;

		background-color: white;
	}

	.burger-container .line:nth-child(1) {
		top: 29%;
	}

	.burger-container .line:nth-child(2) {
		bottom: 29%;
	}

	.burger-container .cross:nth-child(1) {
		transform: translateY(7.2px) rotate(135deg);
	}

	.burger-container .cross:nth-child(2) {
		transform: translateY(-7.2px) rotate(-135deg);
	}

	@media screen and (max-width: 600px) {
		.burger-container {
			height: 2rem;
			width: 2rem;
		}

		.burger-container .line {
			height: 2px;
		}

		.burger-container .cross:nth-child(1) {
			transform: translateY(6px) rotate(135deg);
		}
		.burger-container .cross:nth-child(2) {
			transform: translateY(-6px) rotate(-135deg);
		}
	}
</style>
