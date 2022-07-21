<script>
	// const links = document.querySelectorAll("a");
	// links.forEach((link) => {
	// 	link.addEventListener("mouseleave", () => {
	// 		mouseCursor.classList.remove("link-hover");
	// 	});
	// 	link.addEventListener("mouseenter", () => {
	// 		mouseCursor.classList.add("link-hover");
	// 	});
	// });

	let m = { x: 0, y: 0 };
	let mouseCursor;
	let clicked = false;

	function handleMousemove(event) {
		m.x = event.clientX;
		m.y = event.clientY;
		mouseCursor.style.left = m.x + "px";
		mouseCursor.style.top = m.y + "px";
	}

	function handleMousedown() {
		clicked = true;
	}

	function handleMouseup() {
		clicked = false;
	}
</script>

<svelte:body
	on:mousemove={handleMousemove}
	on:mousedown={handleMousedown}
	on:mouseup={handleMouseup} />

<div bind:this={mouseCursor} class="innerdot" class:active={clicked} />

<style>
	.innerdot {
		opacity: 1;
		width: 13px;
		height: 13px;
		background: var(--bg-lightmode);
		border-radius: 50%;
		position: fixed;
		transform-origin: 50% 50%;
		transform: translate(-50%, -50%);
		pointer-events: none;
		transition: 0.1s cubic-bezier(0, 0.39, 0.7, 1);
		transition-property: width, height;
		z-index: 100;
		cursor: default;
	}

	.active {
		width: 8px;
		height: 8px;
		transition: all 0.1s ease-out;
		transition-duration: 0.1s;
	}

	/* .link-hover {
		opacity: 1;
		background: rgba(26, 26, 26, 0.4);
		transform: scale(3);
		transition: all 0.095s ease-in-out;
		transition-property: background, transform;
	} */
</style>
