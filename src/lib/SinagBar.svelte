<script lang="ts">
	import Icon from "@iconify/svelte";
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="" />
	<link
		href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wdth,wght@0,75..100,300..800;1,75..100,300..800&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<div class="sinag-sticky">
	<div class="logo">
		<img src="https://sinag.dev/assets/img/logo.png" alt="Sinag Logo" />
	</div>
	<div class="contact">
		<ul class="links">
			<li><a href="#facebook"><Icon icon="devicon:facebook" /></a></li>
			<li><a href="#twitter"><Icon icon="skill-icons:twitter" /></a></li>
			<li>
				<a href="#instagram"><Icon icon="skill-icons:instagram" /></a>
			</li>
			<li>
				<a href="#wordpress"><Icon icon="skill-icons:wordpress" /></a>
			</li>
		</ul>
	</div>
</div>

<style lang="scss">
	.sinag-sticky {
		box-sizing: border-box;
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		background-color: #000;
		color: #fff;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);

		font-family: "Open Sans", sans-serif;
		font-variation-settings: "wdth" 85;

		display: flex;
		justify-content: space-between;
		align-items: center;
		padding-inline-start: 1rem;
		padding-inline-end: 1rem;
		padding-block: 0.25rem;
		z-index: 1000;

		img {
			height: 2rem;
			display: block;
		}
	}

	.links {
		display: flex;
		justify-content: space-between;
		gap: 1rem;
		list-style: none;
		line-height: 100%;
		padding: 0 auto 0 auto;
		margin: 0 auto 0 auto;
	}
</style>
