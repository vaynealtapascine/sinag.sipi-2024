<script lang="ts">
	export let size = "small";
	export let type = "filled";
	export let color = "#F98FBF";

	let content = size === "small" ? "IND" : "Independent";
	let flag =
		type === "filled"
			? `background-color: ${color}; color: white;`
			: `color: ${color}; border: 1px solid ${color};`;
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
