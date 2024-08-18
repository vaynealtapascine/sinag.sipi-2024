<script>
	import { Breadcrumb, BreadcrumbItem } from "flowbite-svelte";

	import SinagBar from "$lib/SinagBar.svelte";
	import PageButton from "$lib/PageButton.svelte";

	import PercentDelta from "$lib/img/05b_PercentDelta.png";
	import Population from "$lib/img/05b_Population.png";
	import WAML from "$lib/img/05b_WAML.png";
	import DeptResults from "$lib/img/05b_DSV.png";
	import DeptSum from "$lib/img/05b_Outlay.png";

	import HeaderSquare from "$lib/img/geog-square.png";
	import HeaderWide from "$lib/img/geog-wide.png";

	import "./../../global.scss";
</script>

<svelte:head>
	<title>SINAG • SIPI | Geography</title>
</svelte:head>

<SinagBar>
	<Breadcrumb>
		<BreadcrumbItem href="/sipi/2024" home>SIPI</BreadcrumbItem>
		<BreadcrumbItem href="/sipi/2024/dept-results#geog"
			>Deptwide</BreadcrumbItem
		>
		<BreadcrumbItem>Geog</BreadcrumbItem>
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
					alt="84 voted, with 5 grad voters. There are 119 undergraduates and 32 graduate students."
					class="w-full"
				/>
				<p>
					With an impressive 70% voter turnout, the Geog department
					nets itself a whopping +36% overrepresentation in this
					College election. Its outsized influence no doubt played a
					part in Councilor placements, however, its effects on the
					Standard Bearer positions is perhaps limited by its size.
				</p>
			</div>
			<img
				src={PercentDelta}
				alt="7.08% of the College vs. 9.67% of the vote (+2.59 percentage points or +36.54%)"
				class="flex-shrink w-[clamp(100px,_15vw,_250px)]"
			/>
		</div>
		<img
			src={WAML}
			alt="Weighed Average Minimum Lean of the department. +17.79% SAL, -25.60% BUK, +1.55% Abstain."
			class="rightwide gauge-fade"
		/>
		<p class="rightsmall">
			With a +17% lean in favor of SALiGAN and a -25% lean against BUKLOD,
			the Department maintains its position as a SALiGAN stronghold, whose
			hold is only projected to strengthen to +19%. Despite this however,
			the department appears to be heading the abstentions in the College,
			alongside Kas, with a +1.5% abstention lean.
		</p>
		<img
			src={DeptResults}
			alt="Results as per votes from the Geography department."
			class="full-span"
		/>
		<img
			src={DeptSum}
			alt="Summative of results from Geog department."
			class="leftwide"
		/>
		<p class="leftsmall">
			The Department locks out BUKLOD’s candidates entirely, electing a
			SALiGAN- and Independent-only Council. BUKLOD’s picks are unable to
			net even 16% of the vote and its Councilors are handily beat by 20%
			abstention rate, while its Standard Bearers barely scratch the
			34-36% abstention rate.
		</p>
		<p class="reg-span">
			While Geog has recently been under SALiGAN’s grip and was still able
			to elect its picks this year, it is becoming an increasing concern
			whether the rising tide of abstentions will override that selection
			in the following years. While Geog candidates do very well in the
			Department, their other partymates remain to have to prove
			themselves to the Department to ensure a win. Community engagement
			will have to intensify for both parties to engage voters in this
			Department and maintain or break holds in Geog.
		</p>
		<PageButton
			classNames="rightwide place-self-stretch !my-0"
			title="Kasaysayan ▶"
			description="Full results & analysis"
			href="/sipi/2024/dept-results/kas"
			side="to left"
		/>
		<PageButton
			classNames="leftwide place-self-stretch !mt-0 "
			title="◀ Departmental Results"
			description="Results across all the departments"
			href="/sipi/2024/dept-results#geog"
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
		background: radial-gradient(ellipse at center, #24a516, #0d5402 100%);
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
