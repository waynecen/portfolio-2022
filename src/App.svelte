<script>
	import Cursor from "./Cursor.svelte";
	import ThemeToggle from "./components/ThemeToggle.svelte";
	import Divider from "./components/Divider.svelte";
	import Project from "./components/Project.svelte";
</script>

<Cursor />
<main>
	<nav>
		<a href="/"
			><img src="./src/assets/favicon.ico" class="logo" alt="Logo icon" /></a
		>
		<div class="wrapper">
			<a class="socials" href="https://github.com/waynecen" target="_blank"
				>GitHub</a
			>
			<a class="socials" href="https://linkedin.com/in/waynecen" target="_blank"
				>LinkedIn</a
			>
			<a class="socials" href="https://linkedin.com/in/waynecen" target="_blank"
				>Instagram</a
			>
			<ThemeToggle />
		</div>
	</nav>
	<section>
		<h1 class="header">Hey, I'm Wayne</h1>
		<p class="description">
			I'm a software developer and designer — specializing in designing and
			building accessible, fun, and <span class="magic">eye-catching</span> things for
			the web.
		</p>
		<div class="shift-right">
			<a class="resume" href="/" target="_blank">Resume --></a>
		</div>
		<Divider />
		<div class="wrapper--projects">
			<Project name="The Weather" link="https://the-weather-six.vercel.app/"
				>Weather app</Project
			>
			<Project name="Tenzi" link="https://tenzi-game.vercel.app/"
				>Dice Game</Project
			>
			<Project name="Quizzical" link="https://quizzical-ten.vercel.app/">Trivia Game</Project>
		</div>
	</section>
</main>

<style>
	:global(body) {
		background-color: var(--bg-darkmode);
		color: var(--text-darkmode);
		transition: background-color 0.3s;
	}
	:global(body.dark-mode) {
		background-color: var(--bg-lightmode);
		color: var(--text-lightmode);
	}

	/* Navigation */
	nav {
		display: flex;
		justify-content: space-between;
		background: rgba(0, 0, 0, 0.5);
		padding-top: 16px;
		padding-left: 10%;
		padding-bottom: 16px;
		font-size: 0.9rem;
		position: sticky;
		top: 0;
		z-index: 99;
		backdrop-filter: blur(8px) brightness(200%) opacity(90%);
	}

	.logo {
		display: flex;
		width: 24px;
		height: 24px;
		align-self: left;
		transition: transform 0.225s ease-in-out;
	}

	.logo:hover {
		transform: scale(1.15) rotate3d(1, 1, 1, 360deg);
	}

	.wrapper {
		display: flex;
		flex-direction: row;
		justify-self: flex-end;
		margin-right: 10%;
	}

	.wrapper a {
		margin-right: 16px;
	}

	.socials:hover {
		opacity: 0.8;
	}

	/* About */
	main {
		display: flex;
		flex-direction: column;
		font-family: var(--primary);
		height: 200vmin;
	}

	section {
		margin-top: 10vmin;
		margin-left: 10%;
		margin-right: 10%;
	}

	.header {
		font-size: 1.6rem;
		font-weight: 600;
		margin-bottom: 8px;
	}

	.description {
		font-size: 1rem;
		font-weight: 400;
		max-width: 520px;
		line-height: 1.5rem;
		margin-bottom: 20px;
		color: #a7a7a7;
	}

	/* accent text */
	@keyframes background-pan {
		from {
			background-position: 0% center;
		}

		to {
			background-position: -200% center;
		}
	}

	p > .magic {
		animation: background-pan 5s linear infinite;
		background: linear-gradient(
			to right,
			var(--gradient1),
			var(--gradient2),
			var(--gradient3),
			var(--gradient1)
		);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-size: 200%;
		white-space: nowrap;
		font-weight: 600;
		font-size: 1rem;
	}

	/* Resume link */
	.shift-right {
		width: fit-content;
		transition: all 0.225s ease-out;
	}

	.shift-right:hover {
		transform: translate(4px);
		opacity: 0.7;
	}

	/* Projects */
	.wrapper--projects {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		padding-top: 32px;
	}

	.wrapper--projects {
	}
</style>
