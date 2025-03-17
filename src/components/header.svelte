<script lang="ts">
	let prevIndex = -1;
	let prideFlags: string[] = [
		'linear-gradient(to right,#d95c5c 16.66%, #e08950 0 33.33%, #e5cf63 0 50%, #74b37a 0 66.66%, #5c84c1 0 83.33%, #694ead 0)', // Rainbow Pride
		'linear-gradient(to right,#70c3d9 20%, #e8a3ad 0 40%, #f0f0f0 0 60%, #e8a3ad 0 80%, #70c3d9 0)', // Trans Pride
		'linear-gradient(to right,#d46a96 40%, #b28aad 0 60%, #5073b3 0)', // Bisexual Pride
		'linear-gradient(to right,#d46aa3 33.33%, #e2c077 0 66.66%, #67b5d9 0)', // Pansexual Pride
		'linear-gradient(to right,#2b2b2b 25%, #8c8c8c 0 50%, #e0e0e0 0 75%, #902f7b 0);', // Asexual Pride
		'linear-gradient(to right,#d65555 0 14.28%, #e38b4a 0 28.57%, #e5a85d 0 42.85%, #f0e0e0 0 57.14%, #e597b2 0 71.42%, #e08aa9 0 85.71%, #c76091 0)', // Lesbian
		'linear-gradient(to right,#1b7d64 0 14.28%, #46b598 0 28.57%, #88d3b3 0 42.85%, #e0e7f0 0 57.14%, #7ea0d0 0 71.42%, #685db3 0 85.71%, #5b338d 0)' // Gay
	];

	let currentFlag: string = prideFlags[0]; // Default flag (Rainbow)

	// Function to change flag on hover
	const changeFlag = () => {
		let randomIndex;
		do {
			randomIndex = Math.floor(Math.random() * prideFlags.length);
		} while (randomIndex === prevIndex); // Regenerate if it's the same index

		prevIndex = randomIndex; // Update previous index
		currentFlag = prideFlags[randomIndex]; // Set the new flag
	};
</script>

<header>
	<nav class="be-vietnam-pro-black">
		<div class="logo">
			<img src="/tps-logo.png" alt="" />
			<h3>The Pride Society</h3>
		</div>
		<a class="nav-item outline" style="--flag: {currentFlag};" on:mouseenter={changeFlag} href="/"
			>Home</a
		>
		<a class="nav-item" style="--flag: {currentFlag};" on:mouseenter={changeFlag} href="/About"
			>About Us</a
		>
		<a class="nav-item" style="--flag: {currentFlag};" on:mouseenter={changeFlag} href="/Contact"
			>Contact Us</a
		>
		<a class="nav-item" style="--flag: {currentFlag};" on:mouseenter={changeFlag} href="/Team"
			>Team</a
		>
	</nav>
</header>

<style lang="scss">
	@import url('https://fonts.googleapis.com/css2?family=Be+Vietnam+Pro:wght@900&display=swap');

	//text defaults
	$text-color: black;
	.be-vietnam-pro-black {
		font-family: 'Be Vietnam Pro', sans-serif;
		font-weight: 900;
		font-style: normal;
	}

	header {
		width: 100vw;
		max-width: 100%;
		height: 10vh;
		justify-content: center;
		align-content: center;
		display: flex;
		margin: 0 auto;
		background-color: rgba(78, 78, 78, 0.295);
	}
	nav {
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		align-items: center;
		max-height: 10vh;
		margin: 0 0;
	}
	.nav-item {
		text-decoration: none;
		font-size: clamp(20px, 2vw, 64px);
		color: $text-color;
		display: inline-block;
		transition: font-size 0.5s;
		-webkit-text-stroke: 0.05em white;

		&:hover {
			font-size: clamp(16px, 4vw, 72px);
			background-clip: text;
			background: var(--flag);
			-webkit-background-clip: text;
			-webkit-text-fill-color: transparent;
			animation: wiggle 0.5s ease-in-out infinite;
		}
	}
	.logo {
		display: grid;
		grid-template-columns: 1fr, 1fr;
		justify-content: center;
		align-items: center;
		h3 {
			grid-column: 2;
		}
		img {
			grid-column: 1;
			height: 50px;
			aspect-ratio: 1 / 1;
		}
	}

	@keyframes wiggle {
		0% {
			transform: rotate(0deg);
		}
		20% {
			transform: rotate(-2deg);
		}
		40% {
			transform: rotate(2deg);
		}
		60% {
			transform: rotate(-1deg);
		}
		80% {
			transform: rotate(1deg);
		}
		100% {
			transform: rotate(0deg);
		}
	}
	@media only screen and (max-width: 600px) {
		.logo {
			display: none;
		}
	}
</style>
