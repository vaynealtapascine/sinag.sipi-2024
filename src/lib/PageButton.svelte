<script lang="ts">
	export let title;
	export let description;
	export let href;
	export let side = "to left";
	export let color = "#F6CE52";
	export let classNames;

	let sideAlign = side === "to left" ? "end" : "start";
	let textAlign = side === "to left" ? "right" : "left";
	let shadow =
		side === "to left"
			? "0.25rem 0.25rem 0.5rem 0.25rem #0002"
			: "-0.25rem 0.25rem 0.5rem 0.25rem #0002";
</script>

<a
	{href}
	style="--side:{side}; --side-align: {sideAlign}; --text-align: {textAlign}; --shadow: {shadow}; --color: {color}"
	class="page-button {classNames}"
	data-sveltekit-reload
>
	<h3 class="toc-exclude">{title}</h3>
	<subtitle>{description}</subtitle>
</a>

<style>
	.page-button {
		display: flex;
		line-height: 0.9;
		text-align: var(--text-align);
		flex-direction: column;
		align-items: var(--side-align);
		justify-content: center;
		margin: 2rem 1rem;
		padding: 1rem;
		border: 1px solid var(--color);
		border-radius: 2rem;
		background: linear-gradient(var(--side), var(--color), transparent);
		box-shadow: var(--shadow);
		transition: padding 0.2s;
		color: black;

		h3 {
			padding-bottom: 0.5rem;
		}

		subtitle {
			padding-bottom: 0.25rem;

			.rightwide &,
			.leftsmall & {
				padding-right: 2rem;
			}

			.leftwide &,
			.rightsmall & {
				padding-left: 2rem;
			}
		}

		&:hover {
			background: linear-gradient(
				var(--side),
				var(--color),
				var(--color)
			);
		}

		&.rightwide:hover,
		&.leftsmall:hover {
			padding-right: 1.5rem;
		}

		&.leftwide:hover,
		&.rightsmall:hover {
			padding-left: 1.5rem;
		}
	}
</style>
