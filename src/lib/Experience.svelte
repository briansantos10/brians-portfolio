<script>
	import { mode } from '../shared.svelte';
	let { exp } = $props();
	let active = $state(false);
</script>

<div id="experience" class="container grid" class:active={mode.theme === 'light'}>
	<div class="left">
		<div class="num">{exp.num}</div>
	</div>
	<div class="right">
		<div
			class="top"
			onclick={() => {
				active = !active;
			}}
		>
			<div class="left">
				<div class="title">{exp.title}</div>
				<!-- <span class="role">{exp.role}</span> -->
			</div>
			<i class:active class:light={mode.theme === 'light'} class="fa-solid fa-plus"></i>
		</div>
		<div class="bottom" class:active>
			<p>
				{exp.description}
			</p>
		</div>
	</div>
</div>

<style>
	.grid {
		display: grid;
		grid-template-columns: 1fr 1fr;
	}
	.container {
		border-bottom: 1px solid #ebe9ea38;
		cursor: pointer;
	}
	.container.active {
		border-bottom: 1px solid #14231c43;
	}
	.left .num {
		font-size: 25px;
		font-weight: bold;
	}
	.right {
		display: flex;
		flex-direction: column;
	}
	.top {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
	}
	.top .left {
		display: flex;
		align-items: baseline;
		gap: 1rem;
	}
	.title {
		font-size: 45px;
		font-weight: 500;
	}
	span {
		font-size: 15px;
		font-weight: bold;
	}
	p {
		font-weight: 500;
		cursor: default;
		padding-bottom: 1rem;
	}
	.fa-solid {
		font-size: 17px;
		color: #e9e9e9;
		transition: rotate 300ms ease-in-out;
	}
	.fa-solid.active {
		rotate: 45deg;
	}
	.fa-solid.light {
		color: #14231c;
	}
	/* Improved bottom container styles */
	.bottom {
		max-height: 0; /* Collapsed by default */
		overflow: hidden;
		transition:
			max-height 300ms ease-in-out,
			opacity 300ms ease-in-out;
		opacity: 0;
	}
	.bottom.active {
		max-height: 300px;
		opacity: 1; /* Adjust to fit content */
	}

	@media only screen and (max-width: 768px) {
		.grid {
			grid-template-columns: 1fr 2fr;
		}
	}

	@media only screen and (max-width: 435px) {
		.title {
			font-size: 2.2rem;
		}
	}
	@media only screen and (max-width: 320px) {
		.title {
			font-size: 2rem;
		}
	}
</style>
