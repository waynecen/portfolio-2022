<script>
	import Cursor from "./Cursor.svelte";
</script>

<Cursor />
<main>
	<section class="container--about">
		<h1 class="header">Hey, I'm Wayne,</h1>
		<p class="intro-description">Desc</p>
		<button class="btn--toggle">Toggle Dark-mode</button>
	</section>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		font-family: var(--primary);
		height: 100vmin;
		justify-content: center;
		align-items: center;
	}

	.container--about {
		width: 960px;
	}

	.header {
		font-size: 1.6rem;
		font-weight: 500;
		color: #e9e9e9;
		margin-bottom: 8px;
	}

	.intro-description {
		font-size: 1rem;
		font-weight: 300;
		max-width: 520px;
		line-height: 1.4rem;
	}

	.btn--toggle {
		width: 120px;
		height: 44px;
	}
</style>
