<script>
	import { mode } from '../shared.svelte';
	let { GridChange, themeChange } = $props();

	let expand = $state(false);

	function handleClick() {
		const newGrid = !mode.grid;
		GridChange(newGrid);
	}
	function toggleTheme() {
		const newTheme = mode.theme === 'dark' ? 'light' : 'dark';
		themeChange(newTheme);
	}

	function expandMenu() {
		expand = !expand;
	}
	function closeMenu() {
		setTimeout(() => {
			expand = false;
		}, 500);
	}
	function scrollToSection(sectionId) {
		const section = document.getElementById(sectionId);
		if (section) {
			section.scrollIntoView({ behavior: 'smooth' });
		}
	}
</script>

<!-- svelte-ignore a11y_no_static_element_interactions -->
<!-- svelte-ignore a11y_click_events_have_key_events -->
<header
	class="grid"
	class:active={expand}
	onmouseleave={closeMenu}
	class:light={mode.theme === 'light'}
>
	<div class="top" onclick={expandMenu}>
		Menu <i class="fa-solid fa-plus"></i>
	</div>
	<div class="bottom">
		<div class="links">
			<a href="#home">Home</a>
			<a href="#projects" onclick={scrollToSection}>Projects</a>
			<a href="#experience">Experience</a>
			<a href="#contact">Contact</a>
		</div>
		<div class="toggle_modes">
			<button onclick={handleClick}> [ Grid ] </button>
			<button onclick={toggleTheme}>
				[
				{#if mode.theme === 'dark'}
					Light
				{:else}
					Dark
				{/if}
				]
			</button>
		</div>
	</div>
</header>
<div class="backdrop" class:active={expand}></div>

<style>
	.backdrop {
		position: fixed;
		left: 0;
		background-color: black;
		width: 100vw;
		height: 100vh;
		z-index: 1;
		opacity: 0;
		transition: opacity 300ms ease-in-out;
		pointer-events: none;
	}
	.backdrop.active {
		opacity: 0.2;
	}
	header {
		position: fixed;
		border-radius: 5px;
		background-color: #e9e9e9;
		color: #14231c;
		right: 0.5rem;
		top: 0.5rem;
		width: 89px;
		height: 40px; /* Start with max-height for smooth transition */
		overflow: hidden; /* Ensures content is hidden when collapsed */
		padding: 1rem;
		transition:
			height 300ms ease,
			width 300ms ease; /* Smooth transitions */
		display: flex;
		flex-direction: column;
		z-index: 999;
	}
	header.light {
		background-color: #14231c;
		color: #e9e9e9;
	}
	header.light .top .fa-solid {
		color: #e9e9e9;
	}
	header.light .top {
		color: #e9e9e9;
	}
	header .top {
		cursor: pointer;
		position: absolute;
		right: 0rem;
		top: 0;
		transform: translate(-15%, 50%);
		display: flex;
		align-items: center;
		gap: 0.7rem;
		font-size: 15px;
		font-weight: 500;
		color: #14231c;
	}
	header .bottom {
		display: block;
		opacity: 0;
		transition: opacity 300ms ease;
		height: 100%;
		display: flex;
		flex-direction: column;
		text-align: right;
		margin-top: 2rem;
		justify-content: space-between;
	}

	header.active {
		height: 300px; /* Expanded height */
		width: 180px;
	}
	header .top .fa-solid {
		transition: rotate 300ms ease-in-out;
		color: #14231c;
	}
	header.active .top .fa-solid {
		rotate: 45deg;
	}
	header.active .bottom {
		opacity: 1; /* Fade in bottom content */
	}
	header .links {
		display: flex;
		flex-direction: column;
		font-size: 25px;
		font-weight: 500;
	}
	header .toggle_modes {
		cursor: pointer;
		width: 100%;
		display: flex;
		justify-content: right;
		display: flex;
		gap: 0.5rem;
		opacity: 0.7;
		font-weight: bold;
	}
</style>
