<script>
	import Cursor from "./Cursor.svelte";
	import ThemeToggle from "./components/ThemeToggle.svelte";
</script>

<Cursor />
<main>
	<nav>
		<a href="/"><img src="./src/assets/favicon.ico" class="logo" alt="Logo icon"></a>
		<ThemeToggle />
	</nav>
	<section class="about">
		<h1 class="header">Hey, I'm Wayne</h1>
		<p class="description">
			I'm a software developer and designer — specializing in designing and building accessible, fun, and <span class="magic">eye-catching</span> things for the web. 
		</p>
		<div class="shift-right">
			<a class="resume" href="/" target="_blank">Resume --></a>
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
		z-index: 1;
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
	}

	.about {
		/* width: 960px; */
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
		animation: background-pan 3s linear infinite;
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

	/* resume arrow */
	.resume {
		width: fit-content;
		block-size: fit-content;
	}

	.shift-right {
		width: fit-content;
		transition: transform 0.225s ease-out;
	}

	.shift-right:hover {
		transform: translate(4px);
	}
</style>
