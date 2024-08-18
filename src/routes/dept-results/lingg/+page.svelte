<script>
	import { Breadcrumb, BreadcrumbItem } from "flowbite-svelte";

	import SinagBar from "$lib/SinagBar.svelte";
	import PageButton from "$lib/PageButton.svelte";

	import PercentDelta from "$lib/img/07b_PercentDelta.png";
	import Population from "$lib/img/07b_Population.png";
	import WAML from "$lib/img/07b_WAML.png";
	import DeptResults from "$lib/img/07b_DSV.png";
	import DeptSum from "$lib/img/07b_Outlay.png";

	import HeaderSquare from "$lib/img/lingg-square.png";
	import HeaderWide from "$lib/img/lingg-wide.png";

	import "./../../global.scss";
</script>

<svelte:head>
	<title>SINAG • SIPI | Linguistics</title>
</svelte:head>

<SinagBar>
	<Breadcrumb>
		<BreadcrumbItem href="/sipi/2024" home>SIPI</BreadcrumbItem>
		<BreadcrumbItem href="/sipi/2024/dept-results#lingg"
			>Deptwide</BreadcrumbItem
		>
		<BreadcrumbItem>Lingg</BreadcrumbItem>
	</Breadcrumb>
</SinagBar>

<div class="article">
	<div class="header">
		<picture>
			<source srcset={HeaderWide} media="(min-width: 1024px)" />
			<img src={HeaderSquare} alt="Header" />
		</picture>
	</div>
	<div class="content place-items-center">
		<div class="full-span flex flex-row w-full items-center justify-around">
			<div class="flex-grow">
				<img
					src={Population}
					alt="78 voted, with 0 grad voters. There are 110 undergraduates and 41 graduate students."
					class="w-full"
				/>
				<p>
					With no graduate student voters and a mere -0.47%
					underrepresentation, Lingg is the department with the lowest
					relative representation error of the College, losing only
					0.03 percentage points of voters in proportion to their
					population.
				</p>
			</div>
			<img
				src={PercentDelta}
				alt="7.08% of the College vs. 7.05% of the vote (-0.03 percentage points or -0.47%)"
				class="flex-shrink w-[clamp(100px,_15vw,_250px)]"
			/>
		</div>
		<img
			src={WAML}
			alt="Weighed Average Minimum Lean of the department. +2.86% SAL, -13.90% BUK, +2.12% Abstain."
			class="rightwide gauge-fade"
		/>
		<p class="rightsmall">
			With a +2.86% lean for SALiGAN and -13.90% for BUKLOD, Lingg remains
			SALiGAN’s. However, its lead here wavers in comparison to previous
			years, with a significant number taken up by abstention votes in
			this year compared to the last.
		</p>
		<img
			src={DeptResults}
			alt="Results as per votes from the Linguistics department."
			class="full-span"
		/>
		<img
			src={DeptSum}
			alt="Summative of results from Lingg department."
			class="leftwide"
		/>
		<p class="leftsmall">
			While the lean in favor of SALiGAN is evident especially in Lingg’s
			selected Standard Bearers, the Councilorships is more of a toss-up,
			with BUKLOD’s Labiste tying with SALiGAN’s Ochosa, and the rest not
			quite so far behind.
		</p>
		<p class="reg-span">
			The tides appear to be turning on Lingg’s lean, especially compared
			to the previous years. Time will tell whether intensified engagement
			by the parties will push it over the edge one way or another.
			Further, unlike other Departments, the gap here is much narrower and
			polarization is a significantly smaller problem. It is possible that
			in future elections, Lingg will sway one way or another, depending
			on the efforts the parties will exert in engaging with the
			Department.
		</p>
		<PageButton
			classNames="rightwide place-self-stretch !my-0"
			title="Philosophy ▶"
			description="Full results & analysis"
			href="/sipi/2024/dept-results/philo"
			side="to left"
		/>
		<PageButton
			classNames="leftwide place-self-stretch !mt-0 "
			title="◀ Departmental Results"
			description="Results across all the departments"
			href="/sipi/2024/dept-results#lingg"
			side="to right"
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
		background: radial-gradient(ellipse at center, #0c9653, #025430 100%);
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
		color: white;
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

		:global(:first-child) {
			margin-top: 0;
			margin-bottom: 0;
		}

		h1:first-of-type {
			margin-top: 0;
		}

		h1,
		h2,
		h3 {
			color: white;
		}

		h1 {
			background: linear-gradient(90deg, #590000, transparent);
			background-blend-mode: multiply;
			font-size: clamp(3rem, 6vw, 8rem);
			margin: 0;
		}
	}

	.svg-contain {
		position: relative;
	}

	.dept-size {
		margin: -3rem;
	}

	.hidden {
		clip: rect(1px 1px 1px 1px); /* IE6, IE7 */
		clip: rect(1px, 1px, 1px, 1px);
		padding: 0;
		border: 0;
		height: 1px;
		width: 1px;
		overflow: hidden;
		white-space: nowrap;
	}

	.councilor-matrix {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(240px, auto));
		gap: 1rem;
		justify-content: stretch;
		align-content: center;
	}

	.gauge-fade {
		margin: -2rem -8rem -3rem;
		max-width: calc(100% + 16rem);
	}
</style>
