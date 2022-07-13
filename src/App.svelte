<script>
	import Cursor from "./Cursor.svelte";
	import ThemeToggle from "./components/ThemeToggle.svelte";
</script>

<Cursor />
<main>
	<section class="container--about">
		<h1 class="header">Hey, I'm Wayne,</h1>
		<p class="intro-description">Desc</p>
		<ThemeToggle>O</ThemeToggle>
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

	main {
		display: flex;
		flex-direction: column;
		font-family: var(--primary);
		height: 100vmin;
		justify-content: center;
		align-items: center;
	}

	.header {
		font-size: 1.6rem;
		font-weight: 500;
		margin-bottom: 8px;
	}

	.intro-description {
		font-size: 1rem;
		font-weight: 300;
		max-width: 520px;
		line-height: 1.4rem;
	}
</style>
