<script>
	export let name, link;
</script>

<div class="card">
	<a href={link} target="_blank">
		<div class="card-content">
			<h3 class="card-title">{name}</h3>
			<h4 class="card-subtitle"><slot name="description" /></h4>
			<slot name="tech-stack" />
		</div>
	</a>
</div>

<style>
	.card {
		aspect-ratio: 1.6 / 1;
		border: 0.2vmin solid white;
		cursor: none;
		position: relative;
		width: 30%;
	}

	.card:hover:before {
		background-position: 100% 100%;
		transform: scale(1.08, 1.08);
	}

	.card:hover > .card-content {
		background-position: -10% 0%;
	}

	.card:before {
		background: linear-gradient(
			130deg,
			transparent 0% 33%,
			var(--gradient1) 66%,
			var(--gradient2) 83.5%,
			var(--gradient3) 100%
		);
		background-position: 0% 0%;
		background-size: 300% 300%;
		content: "";
		height: 100%;
		left: 0px;
		position: absolute;
		top: 0px;
		transition: all 350ms ease;
		width: 100%;
		filter: brightness(0.9);
	}

	.card-content {
		background-image: radial-gradient(
			rgba(255, 255, 255, 0.2) 8%,
			transparent 8%
		);
		background-position: 0% 0%;
		background-size: 3vmin 3vmin;
		height: calc(100% - 4vmin);
		padding: 2vmin;
		position: relative;
		transition: background-position 350ms ease;
		width: calc(100% - 5vmin);
	}

	.card-title,
	.card-subtitle {
		color: white;
		font-family: var(--primary);
		font-weight: 400;
		margin: 0px;
	}

	.card-title {
		font-size: 2.4vmin;
		font-weight: 600;
	}

	.card-subtitle {
		font-size: 0.9rem;
		font-weight: 400;
		margin-top: 1vmin;
		margin-bottom: 0vmin;
	}

	.card-subtitle-word {
		display: inline-block;
		margin: 0vmin 0.3vmin;
		opacity: 0;
		position: relative;
		transform: translateY(40%);
		transition: none;
	}

	@media screen and (max-width: 720px) {
		.card {
			width: 100%;
			margin-bottom: 32px;
		}
	}
</style>
