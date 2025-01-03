<script>
	import { mode } from '../shared.svelte';
	import ButtonDark from './ButtonDark.svelte';
	import Spacer from './Spacer.svelte';

	let { project } = $props();
</script>

<div id="projects" class="project grid" class:active={mode.theme === 'light'}>
	<div class="date">{project.date}</div>
	<div class="info">
		<h2>{project.title}</h2>
		<Spacer height="1rem"></Spacer>
		<p>
			{project.description}
		</p>
		<Spacer height="1rem"></Spacer>

		<ButtonDark>View Project</ButtonDark>
	</div>
</div>

<style>
	.project {
		display: grid;
		grid-template-columns: 1fr 1fr;
		padding: 2rem 0;
		border-top: 1px solid #ebe9ea38;
	}
	.project.active {
		border-top: 1px solid #14231c43;
	}
	.date {
		font-size: 8rem;
		opacity: 0.1;
		font-weight: 600;
	}
	.info {
		display: flex;
		flex-direction: column;
		align-items: first baseline;
	}
	h2 {
		font-size: 95px;
		font-weight: 500;
		line-height: 1;
	}
	p {
		font-weight: 500;
	}

	@media only screen and (max-width: 768px) {
		.project {
			grid-template-columns: 1fr;
			padding: 2.5rem 0;
		}
		.date {
			font-size: 10rem;
			line-height: 5rem;
		}
	}
	@media only screen and (max-width: 435px) {
		.date {
			font-size: 5.9375rem;
			line-height: 3rem;
		}
		h2 {
			font-size: 3.5rem;
		}
	}

	@media only screen and (max-width: 375px) {
		.date {
			font-size: 5rem;
			line-height: 3rem;
		}
		h2 {
			font-size: 3.1rem;
		}
	}
	@media only screen and (max-width: 320px) {
		.date {
			font-size: 5rem;
			line-height: 3rem;
		}
		h2 {
			font-size: 2.8rem;
		}
	}
</style>
