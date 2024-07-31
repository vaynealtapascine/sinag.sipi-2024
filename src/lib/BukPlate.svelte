<script lang="ts">
	export let size = "small";
	export let type = "filled";

	let content = size === "small" ? "BUK" : "BUKLOD CSSP";
	let flag =
		type === "filled"
			? `background-color: #698AFF; color: white;`
			: "color: #698AFF; border: 1px solid #698AFF;";
</script>

<span style={flag}>{content}</span>

<style lang="scss">
	span {
		font-family: "Open Sans", sans-serif;
		font-weight: bold;
		font-variation-settings: "wdth" 90;
		vertical-align: 5%;
		padding-left: 0.25rem;
		padding-right: 0.25rem;
		border-radius: 0.25rem;
		font-size: 80%;
	}
</style>
