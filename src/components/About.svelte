<script>
	import AccentText from "./AccentText.svelte";
</script>

<section id="about">
	<div class="flex-row">
		<div class="flex-col">
			<img src="img/portrait-600.png" class="portrait" alt="Wayne
			Cen Portrait">
			<div class="wrapper">
				<h3 class="subheader">Writing</h3>
				<a
				href="https://betterprogramming.pub/lets-code-mubasic-piano-keys-3ac397d3df1d"
				target="_blank" class="article-link">Let's Code: Piano Keys</a>
				<a
				href="https://betterprogramming.pub/lets-code-mubasic-piano-keys-3ac397d3df1d"
				target="_blank" class="article-link">Learning 3D as a product designer</a>
			</div>
		</div>
		<p class="about-me">
			Graduated with a <AccentText><a
				href="https://design.ampd.yorku.ca/" target="_blank">Bachelor of Design</a></AccentText> from York University.
			<br>
			Focused mainly on <AccentText>UX & UI</AccentText> design, dabbled in coding courses.
			<br>
			Fell in love with programming.
			<br>
			Spent a year building projects, to learn how to code.
			<br>
			<AccentText>Passionate</AccentText> about learning, writing, and
			video games.
			<br>
			<AccentText>React</AccentText> and <AccentText>TypeScript</AccentText> are my frameworks of choice.
			<br>
			Currently available for <AccentText>front-end developer</AccentText> roles. 
			<br>
		</p>
	</div>
</section>

<style>
	a:hover {
		color: var(--linkHover);
	}

	.wrapper {
		display: flex;
		flex-direction: column;
		margin-bottom: 32px;
		width: 32ch;
	}

	.flex-row {
		display: flex;
		gap: 48px;
	}

	.flex-col {
		display: flex;
		flex-direction: column;
	}
	
	.portrait {
		width: 320px;
		height: 200px;
		border-radius: 4px;
	}

	.about-me {
		font-family: var(--primary);
		font-weight: 600;
		font-size: 1.8rem;
		color: var(--grey);
		max-width: var(--paragraph-length);
		line-height: 3.2rem;
		margin-top: -8px;
	}
	
	.subheader {
		color: var(--grey);
		font-size: 1rem;
		border-bottom: 1px var(--border) solid;
		margin-top: 32px;
		padding-bottom: 4px;
	}

	.article-link {
		border-bottom: 1px var(--divider) solid;
		padding: 8px 0px;
	}

	a:hover {
		color: white;
		text-decoration: underline;
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
</style>