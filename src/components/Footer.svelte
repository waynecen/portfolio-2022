<section>
	<footer>
		<p class="contact">
			If you'd like to chat, shoot me an email
			<span class="email">
				<a href="mailto:wayne.cen@gmail.com"> wayne.cen@gmail.com </a>
			</span>
		</p>
		<div class="wrapper">
			<a class="socials" href="https://medium.com/@wayne.cen" target="_blank">
				<p>Medium</p>
			</a>
			<a
				class="socials"
				href="https://www.linkedin.com/in/waynercen/"
				target="_blank"
			>
				<p>LinkedIn</p>
			</a>
			<a class="socials" href="https://github.com/waynecen" target="_blank">
				<p>GitHub</p>
			</a>
			<a
				class="socials"
				href="https://www.instagram.com/waynercen/"
				target="_blank"
			>
				<p>Instagram</p>
			</a>
		</div>
	</footer>
</section>

<style>
	footer {
		display: flex;
		justify-content: space-between;
		font-size: 0.9rem;
		font-weight: 600;
	}

	.contact {
		color: var(--fifty-grey);
	}

	.socials {
		opacity: 0.6;
		height: fit-content;
	}

	.socials:hover {
		opacity: 1;
	}

	.email {
		display: flex;
		flex-direction: column;
		font-size: 1.2rem;
		font-weight: 600;
		transition: opacity 0.225s ease-out;
	}

	.email:hover {
		opacity: 0.8;
	}

	.wrapper {
		display: flex;
		flex-direction: row;
	}

	.wrapper a {
		padding: 8px;
		margin-left: 8px;
	}

	@media screen and (max-width: 720px) {
		footer {
			margin-bottom: 32px;
		}

		.contact {
			display: none;
		}

		.email {
			font-size: 1rem;
		}
	}
</style>
