<script>
	import { Breadcrumb, BreadcrumbItem } from "flowbite-svelte";

	import SinagBar from "$lib/SinagBar.svelte";
	import PageButton from "$lib/PageButton.svelte";

	import PercentDelta from "$lib/img/06b_PercentDelta.png";
	import Population from "$lib/img/06b_Population.png";
	import WAML from "$lib/img/06b_WAML.png";
	import DeptResults from "$lib/img/06b_DSV.png";
	import DeptSum from "$lib/img/06b_Outlay.png";

	import HeaderSquare from "$lib/img/kas-square.png";
	import HeaderWide from "$lib/img/kas-wide.png";

	import "./../../global.scss";
</script>

<svelte:head>
	<title>SINAG • SIPI | Kasaysayan</title>
</svelte:head>

<SinagBar>
	<Breadcrumb>
		<BreadcrumbItem href="/sipi/2024" home>SIPI</BreadcrumbItem>
		<BreadcrumbItem href="/sipi/2024/dept-results#kas"
			>Deptwide</BreadcrumbItem
		>
		<BreadcrumbItem>Kas</BreadcrumbItem>
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
					alt="85 voted, with 24 grad voters. There are 85 undergraduates and 91 graduate students."
					class="w-full"
				/>
				<p>
					Despite having the highest graduate student voting rate of
					26%, the Kas department only nets itself a 48% voting rate,
					landing near the lower end of department voting rates. It
					loses out on 0.57 percentage points or nearly 7% of
					representation. However, its impact on the election is not
					negligible.
				</p>
			</div>
			<img
				src={PercentDelta}
				alt="8.25% of the College vs. 7.68% of the vote (-0.57 percentage points or -6.94%)"
				class="flex-shrink w-[clamp(100px,_15vw,_250px)]"
			/>
		</div>
		<img
			src={WAML}
			alt="Weighed Average Minimum Lean of the department. -12.56% SAL, -4.94% BUK, +9.85% Abstain."
			class="rightwide gauge-fade"
		/>
		<p class="rightsmall">
			With aversion to both SALiGAN (-12%) and BUKLOD (-4%) compared to
			the rest of the College, the Kas department lands its votes heavily
			on the side of Abstentions (+10%). This is a trend that continues
			from the previous years.
		</p>
		<img
			src={DeptResults}
			alt="Results as per votes from the Kasaysayan department."
			class="full-span"
		/>
		<img
			src={DeptSum}
			alt="Summative of results from Kas department."
			class="leftwide"
		/>
		<p class="leftsmall">
			As a result, the Department lands nearly no candidates, only
			electing an independent CSSP Rep and BUKLOD’s Pascua for the
			Councilorship, leaving vacancies as far as the eye can see.
		</p>
		<p class="reg-span">
			With Councilorships netting abstentions over 36% (+12% over the
			College average), the aversions in the Weighted Average Minimum Lean
			lends a noticeable dent in what used to be a BUKLOD stronghold,
			landing itself a nearly non-existent Council. A possible explanation
			is that the Department’s aversion to the running Dept. Rep
			Independent Silerio influenced the rest of the candidacies. However,
			the rising trends of abstentions do not end in Kas and, overall, the
			College’s rise in abstention rates are likely to become a worry, as
			early as the next election.
		</p>
		<PageButton
			classNames="rightwide place-self-stretch !my-0"
			title="Linguistics ▶"
			description="Full results & analysis"
			href="/sipi/2024/dept-results/lingg"
			side="to left"
		/>
		<PageButton
			classNames="leftwide place-self-stretch !mt-0 "
			title="◀ Departmental Results"
			description="Results across all the departments"
			href="/sipi/2024/dept-results#kas"
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
		background: radial-gradient(ellipse at center, #99890e, #605a03 100%);
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
