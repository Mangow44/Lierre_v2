<span class="title-container">
	<span class="title">Anaïs Vautier</span>
</span>
<span class="sub-title-container">
	<span class="sub-title">Illustratrice Française</span>
</span>

<style>
	.title-container {
		z-index: 2;

		display: block;
		overflow: hidden;

		text-align: center;

		mix-blend-mode: exclusion;
		color: #d2e8e3;
	}

	.title-container .title {
		display: block;

		transform: translateY(100%);

		animation: title-sliding 0.5s ease forwards;

		font-family: morris, 'Times New Roman', Times, serif;
		font-size: clamp(20px, 10vw, 150px);
		white-space: nowrap;
	}

	.sub-title-container {
		z-index: 2;
		display: block;
		overflow: hidden;

		text-align: center;

		mix-blend-mode: exclusion;
		color: #d2e8e3;
	}

	.sub-title-container .sub-title {
		display: block;

		transform: translateY(100%);

		animation: title-sliding 0.5s ease forwards;
		animation-delay: 0.5s;

		font-family: 'Times New Roman', Times, serif;
		font-size: clamp(12px, 3vw, 120px);
		white-space: nowrap;
	}

	@keyframes title-sliding {
		100% {
			transform: translateY(0);
		}
	}
</style>
