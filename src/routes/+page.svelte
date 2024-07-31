<script>
	import GaugeSwitcher from "./../lib/GaugeSwitcher.svelte";
	import Toc from "svelte-toc";
	import { Breadcrumb, BreadcrumbItem } from "flowbite-svelte";

	import SinagBar from "$lib/SinagBar.svelte";
	import SalPlate from "$lib/SalPlate.svelte";
	import BukPlate from "$lib/BukPlate.svelte";
	import IndPlate from "$lib/IndPlate.svelte";

	import HeaderSquare from "$lib/img/header-square.png";
	import HeaderWide from "$lib/img/header-wide.png";
	import TurnoutPie from "$lib/img/turnout-pie.png";
	import TurnoutTrend from "$lib/img/turnout-trend.png";

	import "./global.scss";
	import PageButton from "$lib/PageButton.svelte";
</script>

<SinagBar>
	<Breadcrumb>
		<BreadcrumbItem home>SIPI</BreadcrumbItem>
	</Breadcrumb>
</SinagBar>

<svelte:head>
	<title
		>SINAG • SIPI: An Analysis of the 2024 CSSP SC Elections Results & Data</title
	>
</svelte:head>
<div class="background-layer"></div>
<div class="article">
	<Toc
		headingSelector=":is(h1,h2,h3):not(.toc-exclude)"
		title=""
		breakpoint={9999}
	/>
	<div class="header">
		<picture>
			<source srcset={HeaderWide} media="(min-width: 1024px)" />
			<img src={HeaderSquare} alt="Header" />
		</picture>
	</div>

	<div class="content">
		<h1 class="hidden full-span">Introduction</h1>
		<p class="reg-span">
			<strong
				>The 2024 College of Social Sciences & Philosophy Student
				Council elections concluded several months ago to a split
				council</strong
			>, with
			<SalPlate size="large" type="" /> taking 8 seats and
			<BukPlate size="large" type="" /> earning 7. Meanwhile, independent candidates
			took two seats while two more remain vacant.
		</p>
		<p class="reg-span">
			In this year's post-elections result analysis, we explore the
			departmental and level data to better understand how students in the
			College voted and what each party can expect, following the trends
			in the past several years.
		</p>
		<h1 class="reg-span">Turnout Trends and Tangents</h1>
		<img
			class="leftwide"
			src={TurnoutPie}
			alt="Turnout Pie Chart"
			height="100%"
		/>
		<div class="commentary leftsmall">
			<h3>This Year's Turnout</h3>
			<p>
				Total turnout for the 2024 elections was 1,107 out of 2,133
				eligible voters, a 51.90% turnout rate. This follows a similar
				declining trend in the past few years, where 2021 saw a turnout
				of 56.65% while 2023 only saw 53.01% of students at the polls.
			</p>
		</div>

		<img
			class="rightwide"
			src={TurnoutTrend}
			alt="Turnout Trend Chart"
			height="100%"
		/>
		<div class="commentary rightsmall">
			<h3>Turnout History</h3>
			<p>
				The Geography department continues its incredible rise in voter
				turnout, this year reaching over 70% voter turnout, dethroning
				PolSc's performance of 64.98% in 2023. PolSc and Psych meanwhile
				maintain a zigzagging trajectory, heavily influencing the
				College's overall turnout in the previous years.
			</p>
			<p>
				A most notable change from previous years, however, is the
				Philosophy department's meteoric fall from having the
				third-highest turnout rate last year to the lowest of all the
				departments this year, possibly attributable to the lack of a
				Philo department representative candidate.
			</p>
		</div>

		<h1 class="reg-span">Collegewide Results</h1>
		<div class="flourish-embed leftwide">
			<div
				class="flourish-embed flourish-parliament"
				data-src="visualisation/18755046"
			>
				<script
					src="https://public.flourish.studio/resources/embed.js"
				></script>
			</div>
		</div>
		<div class="commentary leftsmall">
			<p>
				Breaking <SalPlate size="" type="" />'s hold over the standard
				bearer positions in the past several years, especially over the
				Chairship, <BukPlate size="" type="" /> gained the Chair and Vice
				Chair positions, with independent candidates only able to secure
				the CSSP Representative position and the PolSc department representative
				post. <SalPlate size="" type="" /> still tops the councilorships
				with 4 seats and maintains their now-slimmer majority through a number
				of department representative positions.
			</p>
			<p>
				While the turnout rate continues to trend slightly downwards,
				the number of abstentions slowly continues to rise. For example,
				the Councilor spot in 2021 received only a hair over 100
				abstentions, but now exceeds 200. A similar trend can be found
				across all standard-bearer positions as well.
			</p>
		</div>
		<div class="reg-span">
			<p>
				Each position below will have an interactive graph that charts
				the department and level distribution of votes. You may refine
				which votes you'd like to see by clicking a subsection of the
				graph. On desktop, you can hover for exact numbers.
			</p>
		</div>
		<h2 class="full-span wide-title">Standard Bearers & Councilors</h2>
		<div class="observable-embed rightwide" id="chair_ob">
			<div id="observablehq-chart_chair-ea23e540"></div>

			<link
				rel="stylesheet"
				href="https://cdn.jsdelivr.net/npm/@observablehq/inspector@5/dist/inspector.css"
			/>
			<script type="module">
				import {
					Runtime,
					Inspector,
				} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@5/dist/runtime.js";
				import define from "https://api.observablehq.com/d/6043a4cc8b34ef2e@1879.js?v=4";
				new Runtime().module(define, (name) => {
					if (name === "chart_chair")
						return new Inspector(
							document.querySelector(
								"#observablehq-chart_chair-ea23e540"
							)
						);
				});
			</script>
		</div>
		<div class="commentary rightsmall">
			<h3>Chair <BukPlate /></h3>
			<p>
				The chairship was closely contested with <BukPlate />&nbsp;Macam
				netting the win with 452 votes and <SalPlate />&nbsp;Patawaran
				receiving 425 votes, a mere 27 vote difference. A considerable
				number of voters (230) still abstained however, with PolSc
				providing nearly 25% of the abstentions.
			</p>
			<p>
				While <SalPlate />&nbsp;Patawaran received a relatively
				well-distributed number of votes across the College's eight
				departments, <BukPlate />&nbsp;Macam received over 56% of her
				votes from her home department Psychology, presenting once again
				the sheer gravity of Psych's numbers as the College's largest
				department.
			</p>
		</div>

		<div class="observable-embed leftwide" id="vc_ob">
			<div id="observablehq-chart_vc-ea23e540"></div>
			<link
				rel="stylesheet"
				href="https://cdn.jsdelivr.net/npm/@observablehq/inspector@5/dist/inspector.css"
			/>
			<script type="module">
				import {
					Runtime,
					Inspector,
				} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@5/dist/runtime.js";
				import define from "https://api.observablehq.com/d/6043a4cc8b34ef2e@1879.js?v=4";
				new Runtime().module(define, (name) => {
					if (name === "chart_vc")
						return new Inspector(
							document.querySelector(
								"#observablehq-chart_vc-ea23e540"
							)
						);
				});
			</script>
		</div>
		<div class="commentary leftsmall">
			<h3>Vice Chair <BukPlate /></h3>
			<p>
				The vice chairship is slightly less contested, with a difference
				of 51 votes for both candidates. However, such margins are still
				quite narrow. <SalPlate />&nbsp;Arceo received a slimmer share
				of votes, while
				<strong
					>abstentions for the position rose all the way to over 25%</strong
				>.
			</p>
			<p>
				The vote distribution story remains the same here, with <BukPlate
				/>&nbsp;Felices receiving even more of her votes from Psych and
				even less of her vote share from PolSc.
			</p>
		</div>

		<div class="observable-embed rightwide" id="crep_ob">
			<div id="observablehq-chart_crep-ea23e540"></div>
			<link
				rel="stylesheet"
				href="https://cdn.jsdelivr.net/npm/@observablehq/inspector@5/dist/inspector.css"
			/>
			<script type="module">
				import {
					Runtime,
					Inspector,
				} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@5/dist/runtime.js";
				import define from "https://api.observablehq.com/d/6043a4cc8b34ef2e@1879.js?v=4";
				new Runtime().module(define, (name) => {
					if (name === "chart_crep")
						return new Inspector(
							document.querySelector(
								"#observablehq-chart_crep-ea23e540"
							)
						);
				});
			</script>
		</div>
		<div class="commentary rightsmall">
			<h3>CSSP Rep <IndPlate /></h3>
			<p>
				<IndPlate />&nbsp;Cruz wins the uncontested CSSP Representative
				position with a supermajority. However, she still receives over
				350 abstentions, most of which coming from the Psych department.
			</p>
			<p>
				Her vote distribution, however, is a broad cross-section of the
				College, implying general, widespread support-- an especially
				important point considering the complete vacancy of the USC's
				university-wide positions.
			</p>
		</div>
		<div class="leftwide councilor-matrix">
			<div class="observable-embed" id="ochosa_ob">
				<div id="observablehq-chart_clrOchosa-ea23e540"></div>

				<link
					rel="stylesheet"
					href="https://cdn.jsdelivr.net/npm/@observablehq/inspector@5/dist/inspector.css"
				/>
				<script type="module">
					import {
						Runtime,
						Inspector,
					} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@5/dist/runtime.js";
					import define from "https://api.observablehq.com/d/6043a4cc8b34ef2e@1879.js?v=4";
					new Runtime().module(define, (name) => {
						if (name === "chart_clrOchosa")
							return new Inspector(
								document.querySelector(
									"#observablehq-chart_clrOchosa-ea23e540"
								)
							);
					});
				</script>
			</div>
			<div class="observable-embed" id="gaspar_ob">
				<div id="observablehq-chart_clrGaspar-ea23e540"></div>
				<link
					rel="stylesheet"
					href="https://cdn.jsdelivr.net/npm/@observablehq/inspector@5/dist/inspector.css"
				/>
				<script type="module">
					import {
						Runtime,
						Inspector,
					} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@5/dist/runtime.js";
					import define from "https://api.observablehq.com/d/6043a4cc8b34ef2e@1879.js?v=4";
					new Runtime().module(define, (name) => {
						if (name === "chart_clrGaspar")
							return new Inspector(
								document.querySelector(
									"#observablehq-chart_clrGaspar-ea23e540"
								)
							);
					});
				</script>
			</div>
		</div>
		<div class="commentary leftsmall">
			<h3>Councilors <SalPlate /> <BukPlate /></h3>
			<p>
				Among the councilor candidates, no candidates are voted by more
				than half of the voters, with only <SalPlate />&nbsp;Ochosa and <SalPlate
				/>&nbsp;Gaspar cracking less than one-third of non-voter
				ballots.
			</p>
		</div>
		<div class="rightwide councilor-matrix">
			<div class="observable-embed" id="alfonso_ob">
				<div id="observablehq-chart_clrAlfonso-ea23e540"></div>

				<link
					rel="stylesheet"
					href="https://cdn.jsdelivr.net/npm/@observablehq/inspector@5/dist/inspector.css"
				/>
				<script type="module">
					import {
						Runtime,
						Inspector,
					} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@5/dist/runtime.js";
					import define from "https://api.observablehq.com/d/6043a4cc8b34ef2e@1879.js?v=4";
					new Runtime().module(define, (name) => {
						if (name === "chart_clrAlfonso")
							return new Inspector(
								document.querySelector(
									"#observablehq-chart_clrAlfonso-ea23e540"
								)
							);
					});
				</script>
			</div>
			<div class="observable-embed" id="pascua_ob">
				<div id="observablehq-chart_clrPascua-ea23e540"></div>

				<link
					rel="stylesheet"
					href="https://cdn.jsdelivr.net/npm/@observablehq/inspector@5/dist/inspector.css"
				/>
				<script type="module">
					import {
						Runtime,
						Inspector,
					} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@5/dist/runtime.js";
					import define from "https://api.observablehq.com/d/6043a4cc8b34ef2e@1879.js?v=4";
					new Runtime().module(define, (name) => {
						if (name === "chart_clrPascua")
							return new Inspector(
								document.querySelector(
									"#observablehq-chart_clrPascua-ea23e540"
								)
							);
					});
				</script>
			</div>
			<div class="observable-embed" id="escototo_ob">
				<div id="observablehq-chart_clrEscototo-ea23e540"></div>

				<link
					rel="stylesheet"
					href="https://cdn.jsdelivr.net/npm/@observablehq/inspector@5/dist/inspector.css"
				/>
				<script type="module">
					import {
						Runtime,
						Inspector,
					} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@5/dist/runtime.js";
					import define from "https://api.observablehq.com/d/6043a4cc8b34ef2e@1879.js?v=4";
					new Runtime().module(define, (name) => {
						if (name === "chart_clrEscototo")
							return new Inspector(
								document.querySelector(
									"#observablehq-chart_clrEscototo-ea23e540"
								)
							);
					});
				</script>
			</div>
			<div class="observable-embed" id="labiste_ob">
				<div id="observablehq-chart_clrLabiste-ea23e540"></div>
				<link
					rel="stylesheet"
					href="https://cdn.jsdelivr.net/npm/@observablehq/inspector@5/dist/inspector.css"
				/>
				<script type="module">
					import {
						Runtime,
						Inspector,
					} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@5/dist/runtime.js";
					import define from "https://api.observablehq.com/d/6043a4cc8b34ef2e@1879.js?v=4";
					new Runtime().module(define, (name) => {
						if (name === "chart_clrLabiste")
							return new Inspector(
								document.querySelector(
									"#observablehq-chart_clrLabiste-ea23e540"
								)
							);
					});
				</script>
			</div>
		</div>
		<div class="commentary rightsmall">
			<p>
				The top six candidates are able to net at least a third of
				votes, with <SalPlate />&nbsp;Alfonso and <BukPlate
				/>&nbsp;Pascua able to net over 40% votes, while <SalPlate
				/>&nbsp;Escototo and <BukPlate />&nbsp;Labiste barely cross
				one-thirds.
			</p>
			<p>
				<SalPlate type="" size="full" /> candidates consistently receive
				a broad distribution of votes, while <BukPlate
					type=""
					size="full"
				/> retain their dominance primarily in PolSc and Psych.
			</p>
			<p>
				The Councilorships are quite numerous and have had to be made
				smaller for readability of the rest of the article. If you'd
				like to see and play with them at full size, you can do so <a
					href="https://observablehq.com/d/6043a4cc8b34ef2e"
					target="_blank">here on Observable</a
				>.
			</p>
		</div>
		<div class="leftbar">
			<div class="observable-embed" id="matandanc_ob">
				<div id="observablehq-chart_clrMatandac-ea23e540"></div>
				<link
					rel="stylesheet"
					href="https://cdn.jsdelivr.net/npm/@observablehq/inspector@5/dist/inspector.css"
				/>
				<script type="module">
					import {
						Runtime,
						Inspector,
					} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@5/dist/runtime.js";
					import define from "https://api.observablehq.com/d/6043a4cc8b34ef2e@1879.js?v=4";
					new Runtime().module(define, (name) => {
						if (name === "chart_clrMatandac")
							return new Inspector(
								document.querySelector(
									"#observablehq-chart_clrMatandac-ea23e540"
								)
							);
					});
				</script>
			</div>
		</div>
		<div class="commentary leftmain">
			<p>
				<BukPlate />&nbsp;Matandac finds difficulty reaching one-third
				of voters, with most of his home department of Lingg, remaining
				non-voters for his Councilorship. It remains to be seen for the
				future of the term if this will lead to problems with
				representation or provide a unique perspective for the Student
				Council's endeavors collegewide.
			</p>
		</div>

		<PageButton
			classNames="rightwide"
			side="to left"
			title="Departmental Results ▶"
			description="Department-specific results and trends"
			href="/sipi/dept-results"
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

	.dept-gauge {
		padding: 2rem 0;
	}
</style>
