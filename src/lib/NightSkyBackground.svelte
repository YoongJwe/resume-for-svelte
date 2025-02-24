<script lang="ts">
	type Star = {
		size: number;
		positionX: number;
		positionY: number;
		twinkleDuration: number;
		floatRange: number;
		animationDelay: number;
	};

	const stars: Star[] = Array.from({ length: 500 }, () => ({
		size: Math.random() * 2 + 1,
		positionX: Math.random() * 100,
		positionY: Math.random() * 100,
		twinkleDuration: Math.random() * 10,
		floatRange: Math.random() * 50,
		animationDelay: Math.random() * 10
	}));
</script>

<div class="night-sky-background">
	{#each stars as star}
		<div
			class="star"
			style="width: {star.size}px; height: {star.size}px;
        left: {star.positionX}vw; top: {star.positionY}vh;
        animation-duration: {star.twinkleDuration}s, 10s;
        animation-delay: {star.animationDelay}s;
        transform: translateY({star.floatRange * -10}px) scale(1.2)"
		></div>
	{/each}
</div>

<style>
	.night-sky-background {
		position: fixed;
		width: 100vw;
		height: 100vh;
		z-index: -1;
	}

	.star {
		position: absolute;
		background-color: white;
		border-radius: 50%;
		opacity: 0.8;
		animation-name: twinkle, float;
		animation-iteration-count: infinite;
		animation-direction: normal;
		animation-timing-function: ease-out;
	}

	@keyframes twinkle {
		from {
			opacity: 0.1;
		}
	}

	@keyframes float {
		from {
			transform: translateY(0);
		}
	}
</style>
