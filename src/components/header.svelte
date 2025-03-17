<script lang="ts">
	let prideFlags: string[] = [
		'linear-gradient(to right,red 16.66%, orange 0 33.33%, yellow 0 50%, green 0 66.66%, blue 0 83.33%, indigo 0)', // Rainbow Pride
		'linear-gradient(to right,#00d2ff 20%, #ffa6b9 0 40%, white 0 60%, #ffa6b9 0 80%, #00d2ff 0)', // Trans Pride
		'linear-gradient(to right,#f07 40%, #c49 0 60%, #03a 0)', // Bisexual Pride
		'linear-gradient(to right,#f09 33.33%, gold 0 66.66%, deepskyblue 0)', // Pansexual Pride
		'linear-gradient(to right,black 25%, darkgray 0 50%, white 0 75%, #a50089 0);', // Asexual Pride
		'linear-gradient(to right,red 0 14.28%, #ff7000 0 28.57%, #f93 0 42.85%, white 0 57.14%, #f5a 0 71.42%, #f49 0 85.71%, #e06 0)', // Lesbian
		'linear-gradient(to right,#00916e 0 14.28%, #00d2a9 0 28.57%, #7debbe 0 42.85%, white 0 57.14%, #6eaee7 0 71.42%, #5443d3 0 85.71%, #43117d 0)' // Gay
	];

	let currentFlag: string = prideFlags[0]; // Default flag (Rainbow)

	// Function to change flag on hover
	const changeFlag = () => {
		const randomIndex = Math.floor(Math.random() * prideFlags.length);
		currentFlag = prideFlags[randomIndex];
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
	@import url('https://fonts.googleapis.com/css2?family=Lexend:wght@100..900&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Be+Vietnam+Pro:wght@900&display=swap');

	//text defaults
	$text-color: black;
	.be-vietnam-pro-black {
		font-family: 'Be Vietnam Pro', sans-serif;
		font-weight: 900;
		font-style: normal;
	}

	.lexend-header {
		font-family: 'Lexend', sans-serif;
		font-optical-sizing: auto;
		font-weight: 850;
		font-style: normal;
	}
	header {
		width: 100vw;
		max-width: 100%;
		height: 10vh;
		justify-content: center;
		align-content: center;

		display: flex;
		margin: 0 0;
	}
	nav {
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		align-items: center;
		max-height: 10vh;
		margin: 0 auto;
	}
	.nav-item {
		text-decoration: none;
		font-size: clamp(8px, 2vw, 64px);
		color: $text-color;
		display: inline-block;
		transition: font-size 0.5s;
		-webkit-text-stroke: 1px white;

		&:hover {
			font-size: clamp(16px, 4vw, 72px);
			background-clip: text;
			background: var(--flag);
			-webkit-background-clip: text;
			-webkit-text-fill-color: transparent;
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
	.outline {
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
</style>
