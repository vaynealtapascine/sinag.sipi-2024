<script>
	import { Breadcrumb, BreadcrumbItem } from "flowbite-svelte";

	import SinagBar from "$lib/SinagBar.svelte";
	import PageButton from "$lib/PageButton.svelte";

	import PercentDelta from "$lib/img/04b_PercentDelta.png";
	import Population from "$lib/img/04b_Population.png";
	import WAML from "$lib/img/04a_WAML.png";
	import DeptResults from "$lib/img/04b_DSV.png";
	import DeptSum from "$lib/img/04b_Outlay.png";

	import HeaderSquare from "$lib/img/anthro-square.png";
	import HeaderWide from "$lib/img/anthro-wide.png";

	import "./../../global.scss";
</script>

<svelte:head>
	<title>SINAG • SIPI | Anthropology</title>
</svelte:head>

<SinagBar>
	<Breadcrumb>
		<BreadcrumbItem href="/sipi/2024" home>SIPI</BreadcrumbItem>
		<BreadcrumbItem href="/sipi/2024/dept-results#anthro"
			>Deptwide</BreadcrumbItem
		>
		<BreadcrumbItem>Anthro</BreadcrumbItem>
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
					alt="84 voted, with 5 grad voters. There are 106 undergraduates and 65 graduate students."
					class="w-full"
				/>
				<p>
					With a 49% voting rate and a 5% underrepresentation rate,
					the Anthropology department only slightly wavers in presence
					within the College elections. However, graduate student
					remain distant and difficult to reach in the department,
					with the vast majority of votes made up of undergraduate
					students (over 74% of whom voted).
				</p>
			</div>
			<img
				src={PercentDelta}
				alt="8.02% of the College vs. 7.59% of the vote (-0.43 percentage points or -5.35%)"
				class="flex-shrink w-[clamp(100px,_15vw,_250px)]"
			/>
		</div>
		<img
			src={WAML}
			alt="Weighed Average Minimum Lean of the department. +16.10% SAL, -23.64% BUK, -7.45% Abstain."
			class="rightwide gauge-fade"
		/>
		<p class="rightsmall">
			With the weighted minimum average lean per the last several years,
			Anthro remains a SALiGAN stronghold, with a -23% aversion to BUKLOD
			and a +16% rate in favor of SALiGAN, especially evident through its
			selection of all SALiGAN candidates.
		</p>
		<img
			src={DeptResults}
			alt="Results as per votes from the Anthropology department."
			class="full-span"
		/>
		<img
			src={DeptSum}
			alt="Summative of results from Anthro department."
			class="leftwide"
		/>
		<p class="leftsmall">
			In the Department, Matandac fails to beat Abstain, while the rest of
			BUKLOD is unable to breach 25% of votes in the department.
		</p>
		<p class="reg-span">
			Overall, the trend in Anthropology hints at a trend of polarization
			towards SALiGAN (projected to increase to +35% compared to the rest
			of the College), but not necessarily an increased aversion towards
			BUKLOD (projected to dip slightly to -22%). It is possible that
			deeper divides continue and fractures the Department as a whole, but
			it remains to be seen how political leanings factor in, especially
			with a SALiGAN candidate winning the department representative post,
			along with the efforts of the respective political parties in
			consolidating their bases.
		</p>
		<PageButton
			classNames="rightwide place-self-stretch !my-0"
			title="Geography ▶"
			description="Full results & analysis"
			href="/sipi/2024/dept-results/geog"
			side="to left"
		/>
		<PageButton
			classNames="leftwide place-self-stretch !mt-0 "
			title="◀ Departmental Results"
			description="Results across all the departments"
			href="/sipi/2024/dept-results#anthro"
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
		background: radial-gradient(ellipse at center, #a51616, #540202 100%);
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
