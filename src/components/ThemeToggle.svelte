<script>
	function handleClick() {
		window.document.body.classList.toggle("dark-mode");
	}
</script>

<button class="btn-toggle" on:click={handleClick}>
	<slot />
</button>

<style>
	.btn-toggle {
		background-color: white;
		border: none;
		border-radius: 8px;
		width: 44px;
		height: 44px;
		cursor: none;
	}

	:global(body.dark-mode) .btn-toggle {
		background-color: var(--bg-color);
		color: var(--text-lightmode);
		border: 1px black solid;
		border-radius: 8px;
	}
</style>
