<script>
	export let images = ['furro.gif', 'bea.png', 'sonic.jpg'];
	import { onMount } from 'svelte';
	export let imageSize = '400px';
	export let imageMax = '400px';

	onMount(() => {
		document.documentElement.style.setProperty('--image-size', imageSize);
		document.documentElement.style.setProperty('--image-max', imageMax);
	});
	let i = 0;

	function nextPhoto() {
		i = (i + 1) % images.length;
	}
	function prevPhoto() {
		i = (i - 1) % images.length;
	}
	function AutoSlide() {
		setInterval(nextPhoto, 3000);
	}
	AutoSlide();
</script>

<div class="gallery">
	<div class="image-container" style="transform: translateX({-100 * i}%);">
		{#each images as img}
			<img src={`/${img}`} alt={img} loading="lazy" class="slide" />
		{/each}
	</div>
</div>

<style lang="scss">
	:root {
		--image-width: 900px;
		--image-max: 400px;
		--image-size: = clamp(150px, var(--image-width), var(--image-max));

	}
	.gallery {
		margin: 0 auto;
		display: flex;
		gap: 10px;
		flex-direction: column;
		width: var(--image-size);
		aspect-ratio: 16 / 9;

		overflow: hidden;
	}
	.image-container {
		width: 100%;
		display: flex;
		transition: transform 0.5s;
	}

	.slide {
		width: var(--image-size);
		aspect-ratio: 16 / 9;
		flex-shrink: 0;
	}
</style>
