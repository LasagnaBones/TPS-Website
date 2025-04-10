<!-- src/lib/Timeline.svelte -->
<script lang="ts">
	import { fly } from 'svelte/transition';

	interface EventData {
		title: string;
		description: string;
	}

	const events: { [year: string]: EventData } = {
		1936: {
			title: 'Everything FUCKING EXPLODES',
			description: 'There used to be a lot of history here, now, its all gone.'
		},
		1946: {
			title: 'evertyhing is sitll gone',
			description: 'There used to be a lot of history here, now, its all gone.'
		},
		1956: {
			title: 'evertyhing is sitll gone',
			description: 'There used to be a lot of history here, now, its all gone.'
		},
		1966: {
			title: 'evertyhing is sitll gone',
			description: 'There used to be a lot of history here, now, its all gone.'
		},
		1976: {
			title: 'evertyhing is sitll gone',
			description: 'There used to be a lot of history here, now, its all gone.'
		},
		1986: {
			title: 'evertyhing is sitll gone',
			description: 'There used to be a lot of history here, now, its all gone.'
		},
		1996: {
			title: 'evertyhing is sitll gone',
			description: 'There used to be a lot of history here, now, its all gone.'
		},
		2006: {
			title: 'evertyhing is sitll gone',
			description: 'There used to be a lot of history here, now, its all gone.'
		},
		2016: {
			title: 'evertyhing is sitll gone',
			description: 'There used to be a lot of history here, now, its all gone.'
		}
	};
</script>

<div class="timeline">
	{#each Object.entries(events) as [year, event], index}
		<div class="timelineItem {index % 2 === 0 ? 'left' : 'right'}">
			<div class="content">
				<h3>{year}</h3>
				<h4>{event.title}</h4>
				<p>{event.description}</p>
			</div>
		</div>
		<div class="timelineEmpty {index % 2 === 0 ? 'left' : 'right'}"></div>
	{/each}
</div>

<style lang="scss">
	.timeline {
		display: grid;
		grid-template-columns: 1fr 1fr 50px 1fr 1fr;

		align-items: center;
		max-width: 1200px;
		margin: auto;
		position: relative;
		padding: 20px;
	}

	.timeline::before {
		content: '';
		position: absolute;
		left: 50%;
		width: 10px;
		height: 100%;
		background-color: #ffffff;
		transform: translateX(-50%);
	}
	.pin {
		height: 200px; /* control the size */
		aspect-ratio: 2/3;
		mask:
			conic-gradient(from -30deg at bottom, #0000, #000 1deg 59deg, #0000 60deg) bottom/100% 50%
				no-repeat,
			radial-gradient(circle at 50% calc(100% / 3), #0000 21.5%, #000 22% 44%, #0000 44.5%);
		background: #ec1a23;
	}

	.timelineItem {
		position: relative;
		display: flex;
		flex-direction: column;
		gap: 5px;
		padding: 10px;
		border-radius: 8px;
		background: #f3f4f6;
		max-width: 90%;
	}
	.timelineEmpty {
		position: relative;
		display: flex;
		flex-direction: column;
		gap: 5px;
		max-width: 90%;
	}

	.left {
		grid-column: 1 / 3;
		text-align: right;
		justify-self: end;
		position: relative;
		z-index: 2;
		& ::before {
			z-index: 1;
			content: '';
			position: absolute;
			right: -7%;
			bottom: 50%;
			width: 30px;
			height: 10px;
			background-color: #ffffff;

		}

	}

	.right {
		grid-column: 4 / 6;
		text-align: left;
		justify-self: start;
		& ::before {
			z-index: 1;
			content: '';
			position: absolute;
			left: -7%;
			bottom: 50%;
			width: 30px;
			height: 10px;
			background-color: #ffffff;
		}
	}
</style>
