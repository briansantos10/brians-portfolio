<div id="contact" class="grid contact">
	<div class="left">
		<div class="links">
			<div class="find">Find Me On</div>

			<div class="socials">
				<a href="/">Email</a>
				<a href="/">Instagram</a>
				<a href="/">Linkedin</a>
				<a href="/">GitHub</a>
			</div>
		</div>
	</div>
	<div class="right">
		<h2>Lorem ipsum dolor sit amet adipisicing</h2>
		<a href="/" class="line"><span>Drop Me A line</span><i class="fa-solid fa-arrow-right"></i></a>
	</div>
</div>

<style>
	.contact {
		display: grid;
		grid-template-columns: 1fr 1fr;
	}
	h2 {
		font-size: 100px;
		font-weight: 500;
		padding-bottom: 2rem;
		line-height: 0.9;
	}
	.contact .left {
		position: relative;
	}
	.links {
		position: absolute;
		bottom: 0;
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}
	.links .find {
		opacity: 0.7;
		font-weight: 500;
	}
	.socials {
		display: flex;
		align-items: center;
		gap: 1rem;
	}
	.line,
	.socials a {
		font-size: 1rem;
		position: relative;
		font-weight: 500;
		display: flex inline;
		align-items: center;
		gap: 3rem;
	}
	.fa-solid {
		font-size: 0.8rem;
	}
	.line::before,
	.socials a::before {
		content: ' ';
		width: 100%;
		height: 0.5px;
		background-color: #e9e9e9;
		position: absolute;
		bottom: -1px;
	}
	@media only screen and (max-width: 768px) {
		.contact {
			grid-template-columns: 1fr;
			gap: 8rem;
		}

		.contact .left {
			order: 2; /* Move left section to the bottom */
		}

		.contact .right {
			order: 1; /* Move right section to the top */
		}
	}
	@media only screen and (max-width: 435px) {
		h2 {
			font-size: 3.5rem;
		}
	}
</style>
