<script>
	import { Breadcrumb, BreadcrumbItem } from "flowbite-svelte";

	import SinagBar from "$lib/SinagBar.svelte";
	import PageButton from "$lib/PageButton.svelte";

	import PercentDelta from "$lib/img/10b_PercentDelta.png";
	import Population from "$lib/img/10b_Population.png";
	import WAML from "$lib/img/10b_WAML.png";
	import DeptResults from "$lib/img/10b_DSV.png";
	import DeptSum from "$lib/img/10b_Outlay.png";

	import HeaderSquare from "$lib/img/psych-square.png";
	import HeaderWide from "$lib/img/psych-wide.png";

	import "./../../global.scss";
</script>

<svelte:head>
	<title>SINAG • SIPI | Psychology</title>
</svelte:head>

<SinagBar>
	<Breadcrumb>
		<BreadcrumbItem href="/sipi/2024" home>SIPI</BreadcrumbItem>
		<BreadcrumbItem href="/sipi/2024/dept-results#psych"
			>Deptwide</BreadcrumbItem
		>
		<BreadcrumbItem>Psych</BreadcrumbItem>
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
					alt="324 voted, with 14 grad voters. There are 406 undergraduates and 210 graduate students."
					class="w-full"
				/>
				<p>
					With just barely over 1% overrepresentation, the Psych
					department is one of the most accurately-represented
					departments in the election. However, with over 600 eligible
					voters, its impact in any election is undeniable. Its 324
					voters make waves and greatly modify the landscape for the
					electorate and it looks particularly dire for SALiGAN here.
				</p>
			</div>
			<img
				src={PercentDelta}
				alt="28.88% of the College vs. 29.27% of the vote (+0.39 percentage points or -1.35%)"
				class="flex-shrink w-[clamp(100px,_15vw,_250px)]"
			/>
		</div>
		<img
			src={WAML}
			alt="Weighed Average Minimum Lean of the department. -26.24% SAL, +15.41% BUK, -6.16% Abstain."
			class="rightwide gauge-fade"
		/>
		<p class="rightsmall">
			With a -26% aversion to SALiGAN and a +15% in favor of BUKLOD, its
			numbers stack up and knock out several of SALiGAN’s candidates,
			particularly in the Councilorships, shaking up the rankings in the
			final result.
		</p>
		<img
			src={DeptResults}
			alt="Results as per votes from the Psychology department."
			class="full-span"
		/>
		<img
			src={DeptSum}
			alt="Summative of results from Psych department."
			class="leftwide"
		/>
		<p class="leftsmall">
			Voting for a nearly all-blue council, Psych remains a BUKLOD
			stronghold. All of SALiGAN’s candidates fail to reach 25% and its
			standard-bearers can hardly crack 10%.
		</p>
		<p class="reg-span">
			BUKLOD’s dominance in Psych shows no signs of stopping (projected to
			become +17%), while SALiGAN’s base is projected to continue
			dwindling Collegewide (dropping its loss in the department to only
			-17%). It is unclear, however, whether this is due to BUKLOD
			fielding candidates in Psychology and SALiGAN’s lack thereof, or if
			the effect remains for the rest of BUKLOD’s candidates without their
			Psych co-candidates to pull the department to the polls.
		</p>
		<p class="reg-span">
			Further, of particular note in Psych is its increasing number of
			Abstentions, hitting an all-time high for Councilors (over 32%), a
			trend that appears to be increasing over time alongside the rest of
			the College. With a department so large, its influence hints at the
			Department’s (and College’s) increasing apathy and polarization.
		</p>
		<PageButton
			classNames="rightwide place-self-stretch !my-0"
			title="Sociology ▶"
			description="Full results & analysis"
			href="/sipi/2024/dept-results/socio"
			side="to left"
		/>
		<PageButton
			classNames="leftwide place-self-stretch !mt-0 "
			title="◀ Departmental Results"
			description="Results across all the departments"
			href="/sipi/2024/dept-results#psych"
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
		background: radial-gradient(ellipse at center, #6a0c96, #320254 100%);
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
