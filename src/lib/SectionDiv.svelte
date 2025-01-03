<script>
	let { center, right } = $props();
</script>

<div class="section_name grid">
	<div></div>
	<div class="right">
		<div style="opacity: 1">{center}</div>
		<div style="opacity: 0.7">[ {right} ]</div>
	</div>
</div>

<style>
	.section_name {
		display: grid;
		grid-template-columns: 1fr 1fr;
		padding-bottom: 1rem;
	}
	.right {
		font-size: 15px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		font-weight: bold;
	}
	@media only screen and (max-width: 768px) {
		.section_name {
			grid-template-columns: 1fr 2fr;
		}
	}
</style>
