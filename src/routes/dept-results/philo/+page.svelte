<script>
	import { Breadcrumb, BreadcrumbItem, P } from "flowbite-svelte";

	import SinagBar from "$lib/SinagBar.svelte";
	import PageButton from "$lib/PageButton.svelte";

	import PercentDelta from "$lib/img/08b_PercentDelta.png";
	import Population from "$lib/img/08b_Population.png";
	import WAML from "$lib/img/08b_WAML.png";
	import DeptResults from "$lib/img/08b_DSV.png";
	import DeptSum from "$lib/img/08b_Outlay.png";

	import HeaderSquare from "$lib/img/philo-square.png";
	import HeaderWide from "$lib/img/philo-wide.png";

	import "./../../global.scss";
</script>

<svelte:head>
	<title>SINAG • SIPI | Philosophy</title>
</svelte:head>

<SinagBar>
	<Breadcrumb>
		<BreadcrumbItem href="/sipi/2024" home>SIPI</BreadcrumbItem>
		<BreadcrumbItem href="/sipi/2024/dept-results#philo"
			>Deptwide</BreadcrumbItem
		>
		<BreadcrumbItem>Philo</BreadcrumbItem>
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
					alt="100 voted, with 2 grad voters. There are 176 undergraduates and 54 graduate students."
					class="w-full"
				/>
				<p>
					With over 14% underrepresentation (or a -1.57 percentage
					point loss), Philo ends up as the most underrepresented
					department in the polls. It also holds the lowest voter
					turnout of the eight departments, which is a drastic fall
					from its previous positions, netting peak voter turnouts in
					the previous years. This lack, perhaps, is an effect of
					having no Department Representative candidate running for
					the post.
				</p>
			</div>
			<img
				src={PercentDelta}
				alt="10.78% of the College vs. 9.21% of the vote (-1.57 percentage points or -14.55%)"
				class="flex-shrink w-[clamp(100px,_15vw,_250px)]"
			/>
		</div>
		<img
			src={WAML}
			alt="Weighed Average Minimum Lean of the department. +13.45% SAL, -16.47% BUK, -7.40% Abstain."
			class="rightwide gauge-fade"
		/>
		<p class="rightsmall">
			Netting a +13% lean in favor of SALiGAN and -16% aversion to BUKLOD
			compared to the College average, SALiGAN is in a very strong
			position with this Department. However, this is a downturn compared
			to the previous years, which had a +19% lean for the red party last
			year. While the grasp clearly remains strong, it remains to be seen
			if it is strong enough to stay.
		</p>
		<img
			src={DeptResults}
			alt="Results as per votes from the Philosophy department."
			class="full-span"
		/>
		<img
			src={DeptSum}
			alt="Summative of results from Philo department."
			class="leftwide"
		/>
		<p class="leftsmall">
			Unlike other SALiGAN-dominated departments, Philo’s lack of
			abstentions strongly favors BUKLOD’s lagging Councilor candidates
			and nets them spots in the Council.
		</p>
		<p class="reg-span">
			Philo pulls through for SALiGAN once again, netting 5% of all votes
			across many of their candidates. And while BUKLOD is able to retain
			positions for their Councilors in Philo, it is much more likely to
			be a byproduct of the lack of abstentions rather than their sheer
			numbers. Engagement in this Department is likely needed for SALiGAN
			to either bolster their place in the Department or for BUKLOD to
			regain a foothold here.
		</p>
		<PageButton
			classNames="rightwide place-self-stretch !my-0"
			title="Political Science ▶"
			description="Full results & analysis"
			href="/sipi/2024/dept-results/polsc"
			side="to left"
		/>
		<PageButton
			classNames="leftwide place-self-stretch !mt-0 "
			title="◀ Departmental Results"
			description="Results across all the departments"
			href="/sipi/2024/dept-results#philo"
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
		background: radial-gradient(ellipse at center, #96430c, #542b02 100%);
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
