<script>
	import ButtonDark from './ButtonDark.svelte';
	import ButtonLight from './ButtonLight.svelte';
	import Spacer from './Spacer.svelte';
</script>

<div id="home" class="hero">
	<div class="left">
		<h1>Brian Capellan</h1>
		<Spacer height="1rem"></Spacer>

		<p>
			Lorem ipsum dolor sit, amet consectetur adipisicing elit. Mollitia, maxime quasi adipisci nam
			tenetur in rem error nulla sunt minima nisi quo expedita sed harum?
		</p>
		<Spacer height="1rem"></Spacer>

		<div class="btns">
			<ButtonDark>Download Resume</ButtonDark>
			<ButtonLight>View Projects</ButtonLight>
		</div>
	</div>
	<div class="right" style="opacity: 0">
		<div class="img"></div>
		<div class="socials">
			<small>Let's Connect</small>
			<div class="links">
				<a class="underline" href="/">Email</a>
				<a class="underline" href="/">Instagram</a>
				<a class="underline" href="/">LinkedIn</a>
				<div id="cursor_follower"></div>
			</div>
		</div>
	</div>
</div>

<style>
	.hero {
		display: grid;
		grid-template-columns: 1fr 1fr;
		padding-top: 5.5rem;
	}

	/* Left styles */
	.left {
		display: flex;
		flex-direction: column;
		align-items: baseline;
	}
	h1 {
		font-size: 140px;
		line-height: 0.9;
	}
	p {
		font-weight: 500;
		padding: 1rem 0;
	}
	.btns {
		display: flex;
		gap: 1rem;
	}

	/* Right Styles */
	.right {
		display: flex;
		flex-direction: column;
	}
	.img {
		flex: 0.8;
		width: 100%;
		height: 100%;
		background-color: #ebeaeb;
		opacity: 0.8;
		border-radius: 10px;
	}
	.socials {
		flex: 0.2;
	}
	small {
		display: inline-block;
		font-size: 15px;
		font-weight: bold;
		opacity: 0.7;
	}
	.links {
		display: flex;
		gap: 0.7rem;
	}
	.underline {
		display: inline-block;
		position: relative; /* Needed for positioning the pseudo-element */
	}
	.underline::after {
		content: ''; /* Creates the pseudo-element */
		position: absolute;
		left: 0;
		bottom: 0; /* Positions the underline below the text */
		height: 2px; /* Thickness of the underline */
		width: 0; /* Start with no width */
		background-color: #e9e9e9; /* Underline color */
		transition: width 0.3s ease-in-out; /* Animation for the underline */
	}
	.underline:hover::after {
		width: 100%; /* Expands the underline on hover */
	}
	@media only screen and (max-width: 768px) {
		h1 {
			font-size: 120px;
		}
		.hero {
			display: grid;
			grid-template-columns: 1fr;
			padding-top: 5.5rem;
		}
	}

	@media only screen and (max-width: 435px) {
		h1 {
			font-size: 4em;
		}
		.btns {
			flex-wrap: wrap;
		}
	}
</style>
