<script>
	import { mode } from '../shared.svelte';
</script>

<div class="lines grid" class:hidden={!mode.grid}>
	<div class="col"></div>
	<div class="col"></div>
	<div class="col"></div>
	<div class="col"></div>
	<div class="col"></div>
	<div class="col"></div>
	<div class="col"></div>
	<div class="col"></div>
</div>

<style>
	.lines {
		width: 100%;
		height: 100vh;
		position: fixed;
		max-width: 1450px;

		display: grid;
		grid-template-columns: repeat(8, 1fr);
		column-gap: 1.2rem;
		pointer-events: none;
		z-index: 10000;
	}
	.col {
		border-left: 0.1px solid red;
		border-right: 0.1px solid red;
		width: 100%;
		height: 100%;
		opacity: 0.2;
	}

	.lines.hidden {
		display: none;
	}

	@media only screen and (max-width: 768px) {
		.lines {
			grid-template-columns: repeat(4, 1fr);
		}
	}
</style>
