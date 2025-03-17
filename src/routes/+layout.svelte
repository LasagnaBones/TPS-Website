<script lang="ts">
	import '../app.css';
	import Header from '../components/header.svelte';
	let { children } = $props();
</script>

<div class="setting">
	<Header />
	<main>
		{@render children()}
	</main>
</div>
<footer>gaming &trade; 2025</footer>

<style>
	/* .setting {
		--checkerboard1: #c1a4da;
		--checkerboard2: #9a77c0;
		width: 100%;
		height: 100%;
		min-height: 95vh;
		background: conic-gradient(
			var(--checkerboard1) 90deg,
			var(--checkerboard2) 90deg 180deg,
			var(--checkerboard1) 180deg 270deg,
			var(--checkerboard2) 270deg
		);
		background-repeat: repeat;
		background-size: 120px 120px;
		background-position: top left;
	} */

	.setting {
		width: 100%;
		height: 100%;
		min-height: 95vh;
		
		background-image: url(/scenery.jpg);
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
	}

	main {
		margin: 0 auto;
		display: flex;
		align-items: center;
		max-width: 100%;
		min-width: 500px;
		width: 100%;
		flex-direction: column;
		background-size: cover;
		text-align: center;
	}
</style>
