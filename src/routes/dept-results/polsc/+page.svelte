<script>
	import { Breadcrumb, BreadcrumbItem, P } from "flowbite-svelte";

	import SinagBar from "$lib/SinagBar.svelte";
	import PageButton from "$lib/PageButton.svelte";

	import PercentDelta from "$lib/img/09b_PercentDelta.png";
	import Population from "$lib/img/09b_Population.png";
	import WAML from "$lib/img/09b_WAML.png";
	import DeptResults from "$lib/img/09b_DSV.png";
	import DeptSum from "$lib/img/09b_Outlay.png";

	import HeaderSquare from "$lib/img/polsc-square.png";
	import HeaderWide from "$lib/img/polsc-wide.png";

	import "./../../global.scss";
</script>

<svelte:head>
	<title>SINAG • SIPI | Political Science</title>
</svelte:head>

<SinagBar>
	<Breadcrumb>
		<BreadcrumbItem href="/sipi/2024" home>SIPI</BreadcrumbItem>
		<BreadcrumbItem href="/sipi/2024/dept-results#polsc"
			>Deptwide</BreadcrumbItem
		>
		<BreadcrumbItem>PolSc</BreadcrumbItem>
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
					alt="228 voted, with 1 grad voter. There are 317 undergraduates and 77 graduate students."
					class="w-full"
				/>
				<p>
					With over 2.12 percentage points of overrepresentation
					(+11%), PolSc is the second most overrepresented Department,
					trailing only Geog’s gargantuan 36% overrepresentation
					(+2.59p.p.). The Department also earns itself second highest
					turnout at 57%, though still astonishingly distant from
					Geog’s 70%.
				</p>
			</div>
			<img
				src={PercentDelta}
				alt="18.47% of the College vs. 20.60% of the vote (+2.12 percentage points or +11.50%)"
				class="flex-shrink w-[clamp(100px,_15vw,_250px)]"
			/>
		</div>
		<img
			src={WAML}
			alt="Weighed Average Minimum Lean of the department. -6.56% SAL, -5.81% BUK, -1.43% Abstain."
			class="rightwide gauge-fade"
		/>
		<p class="rightsmall">
			With a -6% aversion to SALiGAN and -5% aversion to BUKLOD, the
			Department clearly remains in favor of Independents and holds votes
			cutting across parties. While BUKLOD edges out wins in the Standard
			Bearer positions, the Councilorships are a toss-up, with Ochosa and
			Pascua pulling ahead of the pack with leads over 50% and the rest
			falling short of 36%.
		</p>
		<img
			src={DeptResults}
			alt="Results as per votes from the Political Science department."
			class="full-span"
		/>
		<img
			src={DeptSum}
			alt="Summative of results from PolSc department."
			class="leftwide"
		/>
		<p class="leftsmall">
			Overall, PolSc’s results are an unsurprising mix across both parties
			and lower-than-average abstention rates that claim no losses across
			all candidates.
		</p>
		<p class="reg-span">
			PolSc remains particularly unpolarized, suggesting a different
			voting strategy compared to other departments. While its abstentions
			are nowhere near as severe as those in Psych and Kas, PolSc retains
			a sense of skepticism that shows with its higher-than-average
			abstentions for the Standard Bearer positions.
		</p>
		<p class="reg-span">
			As a large and swingy Department, perhaps different strategies will
			fare better in the future, as neither party appears mete a foothold
			in the Department as of yet.
		</p>
		<PageButton
			classNames="rightwide place-self-stretch !my-0"
			title="Psychology ▶"
			description="Full results & analysis"
			href="/sipi/2024/dept-results/psych"
			side="to left"
		/>
		<PageButton
			classNames="leftwide place-self-stretch !mt-0 "
			title="◀ Departmental Results"
			description="Results across all the departments"
			href="/sipi/2024/dept-results#polsc"
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
		background: radial-gradient(ellipse at center, #0c4596, #021c54 100%);
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
