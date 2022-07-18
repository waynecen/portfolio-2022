<script>
	import Cursor from "./Cursor.svelte";
	import Divider from "./components/Divider.svelte";
	import Project from "./components/Project.svelte";
	import Footer from "./components/Footer.svelte";
</script>

<Cursor />
<main>
	<nav>
		<a href="/"><img src="img/favicon.ico" class="logo" alt="Logo icon" /></a>
	</nav>
	<section class="about">
		<h1 class="header">
			Hey, I'm Wayne <img
				src="/img/hand-wave-emoji.png"
				class="emoji--handwave"
				alt="Hand wave emoji"
			/>
		</h1>
		<p class="description">
			I'm a software developer and designer — specializing in designing and
			building accessible, fun, and <span class="magic">eye-catching</span> things for
			the web.
		</p>
		<div class="shift-right">
			<a
				class="resume"
				href="https://drive.google.com/file/d/1Xcp28qiHAozYg7DSoIP8xLjTqj0Zzo-E/view?usp=sharing"
				target="_blank">Resume --></a
			>
		</div>
	</section>
	<Divider />
	<h2 class="header--projects">Selected Work</h2>
	<section class="projects">
		<Project name="Tenzi" link="https://tenzi-game.vercel.app/"
			><p slot="description">
				A game of rolling dice quickly until you hold ten dice of equal value
			</p>
			<p>Built with React</p></Project
		>
		<Project name="The Weather" link="https://the-weather-six.vercel.app/"
			><p slot="description">
				Search the weekly weather forecast for any location
			</p>
		</Project>
		<Project name="Quizzical" link="https://quizzical-ten.vercel.app/"
			><p slot="description">Multiple choice trivia game</p></Project
		>
	</section>
	<Divider />
	<Footer />
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
		width: 20px;
		height: 20px;
		align-self: left;
		transition: transform 0.225s ease-in-out;
	}

	.logo:hover {
		transform: scale(1.15) rotate3d(1, 1, 1, 360deg);
	}

	/* About */
	.about {
		margin-top: 10vmin;
	}

	main {
		display: flex;
		flex-direction: column;
		font-family: var(--primary);
	}

	:global(section) {
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
		font-weight: 700;
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
	.header--projects {
		margin-left: 10%;
		margin-bottom: 16px;
		color: var(--fifty-grey);
		font-weight: 600;
		font-size: 1rem;
	}

	.projects {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}

	@keyframes handwave {
		from {
			transform: rotate(0deg);
		}
		50% {
			transform: rotate(45deg);
		}
		to {
			transform: rotate(0deg);
		}
	}
	.emoji--handwave {
		width: 24px;
		transition: transform 0.3s ease-out;
	}

	.emoji--handwave:hover {
		animation: handwave 0.4s linear infinite;
	}
</style>
