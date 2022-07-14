<script>
	export let name, desc;

	// const subtitle = document.getElementsByClassName("card-subtitle")[0];

	// const createWord = (text, index) => {
	// 	const word = document.createElement("span");

	// 	word.innerHTML = `${text}`;
	// 	word.classList.add("card-subtitle-word");
	// 	word.style.transitionDelay = `${index * 40}ms`;

	// 	return word;
	// };

	// const addWord = (text, index) => subtitle.appendChild(createWord(text, index));

	// const createSubtitle = (text) => text.split(" ").map(addWord);
	// // createSubtitle('Project description goes here');
</script>

<div class="card">
	<div class="card-content">
		<h3 class="card-title">{name}</h3>
		<h4 class="card-subtitle"><slot /></h4>
	</div>
</div>

<style>
	.card {
		aspect-ratio: 1 / 1;
		border: 0.2vmin solid white;
		cursor: pointer;
		position: relative;
		width: 30vmin;
	}

	.card:hover:before {
		background-position: 100% 100%;
		transform: scale(1.08, 1.08);
	}

	.card:hover > .card-content {
		background-position: -10% 0%;
	}

	.card:hover > .card-content > .card-subtitle > .card-subtitle-word {
		opacity: 1;
		transform: translateY(0%);
		transition: opacity 0ms, transform 200ms cubic-bezier(0.9, 0.06, 0.15, 0.9);
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
		z-index: 1;
	}

	.card-content {
		background-image: radial-gradient(
			rgba(255, 255, 255, 0.2) 8%,
			transparent 8%
		);
		background-position: 0% 0%;
		background-size: 3vmin 3vmin;
		height: calc(100% - 6vmin);
		padding: 3vmin;
		position: relative;
		transition: background-position 350ms ease;
		width: calc(100% - 6vmin);
		z-index: 2;
	}

	.card-title,
	.card-subtitle {
		color: white;
		font-family: var(--primary);
		font-weight: 400;
		margin: 0px;
	}

	.card-title {
		font-size: 3vmin;
	}

	.card-subtitle {
		font-size: 1rem;
		margin-top: 1vmin;
	}

	.card-subtitle-word {
		display: inline-block;
		margin: 0vmin 0.3vmin;
		opacity: 0;
		position: relative;
		transform: translateY(40%);
		transition: none;
	}
</style>
