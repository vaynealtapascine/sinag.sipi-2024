<script>
	import Toc from "svelte-toc";
	import { Breadcrumb, BreadcrumbItem } from "flowbite-svelte";

	import SinagBar from "$lib/SinagBar.svelte";
	import SalPlate from "$lib/SalPlate.svelte";
	import BukPlate from "$lib/BukPlate.svelte";
	import IndPlate from "$lib/IndPlate.svelte";

	import HeaderSquare from "$lib/img/header-square.png";
	import HeaderWide from "$lib/img/header-wide.png";
	import Author from "$lib/img/author.jpg";

	import "./../global.scss";
	import PageButton from "$lib/PageButton.svelte";
	import Page from "../+page.svelte";
</script>

<SinagBar>
	<Breadcrumb>
		<BreadcrumbItem href="/sipi" home>SIPI</BreadcrumbItem>
		<BreadcrumbItem href="/sipi/dept-results">Deptwide</BreadcrumbItem>
		<BreadcrumbItem>Conclusion</BreadcrumbItem>
	</Breadcrumb>
</SinagBar>

<svelte:head>
	<title>SINAG • SIPI | Final Notes</title>
</svelte:head>
<div class="background-layer"></div>
<div class="article">
	<div class="header">
		<picture>
			<source srcset={HeaderWide} media="(min-width: 1024px)" />
			<img src={HeaderSquare} alt="Header" />
		</picture>
	</div>

	<div class="content">
		<PageButton
			classNames="leftwide place-self-stretch !mt-0 "
			title="◀ Departmental Results"
			description="Results across all the departments"
			href="/sipi/dept-results"
			side="to right"
		/>
		<div class="reg-span">
			<h1 class="mb-6">Conclusion</h1>
			<p>
				Overall, the composition of the new College of Social Sciences &
				Philosophy Student Council is definitely a more mixed bag than
				perhaps either party would like. Psychology continues to
				exercise a tremendous kind of gravity on election results, while
				both polarization and apathy are hinted by several departments
				locking out entire parties from the Council under their votes.
			</p>
			<p>
				Perhaps mirroring votes in the unitwide USC elections, where the
				entirety of the UPD USC remains vacant, save for local college
				representatives, abstentions continue to trend upwards, claiming
				only 10% of votes in 2022 and now well past 20%. Political
				participation remains steep in the College, unlike much of
				Diliman. However, it is unclear if students are satisfied with
				the candidates they are receiving.
			</p>
			<p>
				What it <em>is</em> clear is that, while <SalPlate
					type=""
					size=""
				/> holds what is a majority in the Council, with <BukPlate
					type=""
					size=""
				/>'s standard bearer's at the helm, a strong need for consensus
				will be needed to get things done. Whether or not such a
				consensus will be met is a matter of both history and
				cooperation, with now several years of heavily mixed Councils
				showing some level of cooperation.
			</p>
			<p>
				But will the new Council follow suit following <SalPlate
					type=""
					size=""
				/>'s break in headship? All eyes on the Council as a new school
				year opens and CSSP FST Month, the Council's first flagship
				project of recent academic years, draws close.
			</p>
		</div>
		<div class="authorial-box reg-span grid grid-cols-[1fr,4fr] gap-4">
			<img src={Author} alt="Author" height="128px" width="128px" />
			<div class="text-box">
				<h3>Article Writer and Data Journalist</h3>
				<p>
					This article, its figures, its design language, and analysis
					were written, designed, and programmed by <a
						href="https://carrd.vayne.garden/"
						target="_blank"
						><strong>Vayne Altapascine del Rosario</strong></a
					>
					over the course of the past two months (June to July 2024). Data
					was retrieved by request from the CSSP Office of Student Affairs.
					Visualizations were written and programmed through
					<a href="https://d3js.org/" target="_blank">D3.js</a> (both
					as a standalone library and as a component of
					<a href="https://observablehq.com/" target="_blank"
						>Observable</a
					>) and
					<a href="https://flourish.studio/" target="_blank"
						>Flourish</a
					>. Website is powered by
					<a href="https://svelte.dev/">Svelte</a>.
				</p>
				<p class="pb-0">
					<strong
						>If you'd like to see more in-depth data analysis in the
						future, help support and fund this work by donating to
						SINAG or directly to Vayne <a
							href="https://carrd.vayne.garden/#support"
							target="_blank">here</a
						>.</strong
					>
				</p>
			</div>
		</div>
		<PageButton
			classNames="rightwide place-self-stretch"
			title="Back to SINAG ▶"
			description="to SINAG's Wordpress site"
			href="https://csspsinag.wordpress.com/"
			side="to left"
		/>
	</div>
</div>

<style lang="scss">
	:global(body) {
		margin: 0;
		padding: 0;
		overflow-x: hidden;
	}

	:global(body::before) {
		content: "";
		position: fixed;
		top: -25lvh;
		left: 0;
		width: 100lvw;
		height: 150lvh;
		background: radial-gradient(ellipse at center, #fff, #d5d5d5 100%);
		background-repeat: no-repeat;
		background-position: center;
		overflow: hidden;
		z-index: -1;
	}

	.header {
		width: 100vw;
		mask-image: linear-gradient(to bottom, white 90%, transparent);

		picture,
		img {
			display: block;
			width: max(100vw, 100%);
			max-height: 97.5vh;
			object-fit: cover;
			object-position: center;
		}
	}

	.article {
		margin: 0 0 0 0;
		width: 100%;
		padding: 0;
		color: black;
	}

	.content {
		width: clamp(15rem, 100%, 60vmax);
		@media screen and (min-width: 1080px) {
			width: 80vw;
		}
		padding: 2rem min(5vw, 2rem);
		margin: -2rem auto 0 auto;
		box-sizing: border-box;
		font-family: "Open Sans", sans-serif;
		display: grid;
		gap: 1rem;
		grid-auto-flow: dense;
		align-items: center;
		justify-content: center;
		grid-template-columns:
			[full-start leftbar-start rightmain-start leftwide-start rightsmall-start]
			minmax(0, 1fr)
			[content-span-start]
			minmax(5rem, 24ch)
			[leftbar-end leftmain-start rightwide-start rightsmall-end]
			minmax(5rem, 24ch)
			[rightbar-start rightmain-end leftwide-end leftsmall-start]
			minmax(5rem, 24ch)
			[content-span-end]
			minmax(0, 1fr)
			[full-end rightbar-end leftmain-end rightwide-end leftsmall-end];

		:global(.reg-span) {
			grid-column: content-span;
		}

		:global(.leftbar) {
			grid-column: leftbar;
			@media screen and (max-width: 1080px) {
				grid-column: full;
			}
		}

		:global(.leftmain) {
			grid-column: leftmain;
			@media screen and (max-width: 1080px) {
				grid-column: full;
			}
		}

		:global(.leftwide) {
			grid-column: leftwide;
			@media screen and (max-width: 1080px) {
				grid-column: full;
			}
		}

		:global(.leftsmall) {
			grid-column: leftsmall;
			@media screen and (max-width: 1080px) {
				grid-column: full;
			}
		}

		:global(.rightbar) {
			grid-column: rightbar;
			@media screen and (max-width: 1080px) {
				grid-column: full;
			}
		}

		:global(.rightmain) {
			grid-column: rightmain;
			@media screen and (max-width: 1080px) {
				grid-column: full;
			}
		}

		:global(.rightwide) {
			grid-column: rightwide;

			@media screen and (max-width: 1080px) {
				grid-column: full;
			}
		}

		:global(.rightsmall) {
			grid-column: rightsmall;
			@media screen and (max-width: 1080px) {
				grid-column: full;
			}
		}

		:global(.full-span) {
			grid-column: full;
		}
	}

	.authorial-box {
		background-color: #dcdcdc;
		padding: 2rem;
		border-radius: 1rem;
	}
</style>
