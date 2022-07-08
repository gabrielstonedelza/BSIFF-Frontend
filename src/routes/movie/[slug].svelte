<script context="module">
	export async function load({ fetch, params }) {
		const res = await fetch(`https://rvci.xyz/film_detail/${params.slug}/`, {
			headers: {
				'content-type': 'application/json',
				accept: 'application/json'
			}
		});
		const movieDetail = await res.json();

		if (res.ok) {
			return {
				props: {
					movieDetail
				}
			};
		}
		return movieDetail;
	}
</script>

<script>
	export let movieDetail;
	import { fly } from 'svelte/transition';
	import eye from '../../assets/images/icons/view.png';
	import play from '../../assets/images/icons/play-button.png';

	let playButtonClicked = false;
	let canDownload = 'nodownload';

	const handlePlayButton = () => {
		playButtonClicked = true;
	};
	const handleCloseVideoContainer = () => {
		playButtonClicked = false;
	};
	let screeningDays = [7, 20, 21, 22, 23, 24, 25];

	let today = new Date();
	let tday = today.getDay();
	let tmonth = today.getMonth() + 1;
</script>

<svelte:head>
	<title>BSIFF | {movieDetail.title}</title>
</svelte:head>

<div
	class="movie-details"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
>
	{#if playButtonClicked}
		<section class="video-container">
			<!-- svelte-ignore a11y-media-has-caption -->
			<video
				controls
				controlsList={canDownload}
				autoplay="true"
				width="80%"
				height="80%"
				oncontextmenu="return false;"
			>
				<source src={movieDetail.get_movie_trailer} type="video/mp4" />
				<!-- {#if screeningDays.includes(7)}
					<source src={movieDetail.get_full_movie} type="video/mp4" />
				{:else}
					<source src={movieDetail.get_movie_trailer} type="video/mp4" />
				{/if} -->
			</video>
			<p class="closebut" on:click={handleCloseVideoContainer}>X</p>
		</section>
	{/if}
	<div class="img-container">
		<img src={movieDetail.get_movie_poster} alt={movieDetail.title} />
	</div>
	<div class="txt-container">
		<div class="title-views">
			<h1>{movieDetail.title}</h1>
			|
			<div class="for-eye">
				<img src={eye} alt="" />
				<p>{movieDetail.views}</p>
			</div>
		</div>
		<small>
			{movieDetail.duration} | {movieDetail.country}
		</small>
		<span class="play-button">
			<img src={play} alt="" on:click={handlePlayButton} />
		</span>
		<h3>Overview</h3>
		<div class="description">
			<p>
				{movieDetail.description}
			</p>
		</div>
		<h3>Producers</h3>
		<div class="producers">
			{movieDetail.producers}
		</div>
		<h3>Writers</h3>
		<div class="producers">
			{movieDetail.writers}
		</div>
		<h3>Directors</h3>
		<div class="producers">
			{movieDetail.directors}
		</div>
		<h3>Key Casts</h3>
		<div class="producers">
			{movieDetail.key_casts}
		</div>
	</div>
	<br />
</div>

<style lang="scss">
	* {
		box-sizing: border-box;
	}
	.movie-details {
		width: 100%;
		height: 100%;
		background-color: rgb(3, 3, 3);
		display: flex;
		gap: 1rem;
		justify-content: center;
		flex-wrap: wrap;
		padding-top: 40px;
		padding-bottom: 20px;
		position: relative;
		.video-container {
			top: 0;
			position: fixed;
			width: 100%;
			height: 100%;
			background-color: rgba(0, 0, 0, 0.8);
			z-index: 1000;
			display: flex;
			justify-content: center;
			align-items: center;
			gap: 1rem;
			.video {
				border-radius: 24px;
				outline: none;
			}
			.closebut {
				color: #c8a461;
				font-size: 50px;
				cursor: pointer;
				transition: ease 0.5s;
				&:hover {
					transform: rotate(90deg);
				}
			}
		}

		.img-container {
			img {
				border-radius: 34px;
				width: 100%;
				height: 100%;
				padding: 20px;
			}
		}
		.txt-container {
			width: 50%;
			display: flex;
			flex-direction: column;
			gap: 1rem;
			color: #c8a461;
			.title-views {
				display: flex;
				align-items: center;
				gap: 1rem;
				h1 {
					padding: 1rem 0rem 2rem;
				}
				img {
					color: #c8a461 !important;
					width: 30px;
					height: 30px;
				}
				.for-eye {
					display: flex;
					align-items: center;
					gap: 0.5rem;
				}
			}
			.play-button {
				cursor: pointer;
				img {
					width: 50px;
					height: 50px;
				}
			}
			.description {
				font-size: 21px;
				line-height: 1.1666666667;
				letter-spacing: 0.009em;
			}
		}
	}

	@media (max-width: 688px) {
		.movie-details {
			.video-container {
				.closebut {
					color: #c8a461;
					font-size: 20px;
					cursor: pointer;
					transition: ease 0.5s;
					&:hover {
						transform: rotate(90deg);
					}
				}
			}
			.txt-container {
				.title-views {
					h1 {
						font-size: 20px;
					}
					img {
						color: #c8a461 !important;
						width: 20px;
						height: 20px;
					}
				}
				.play-button {
					cursor: pointer;
					img {
						width: 40px;
						height: 40px;
					}
				}
				.description {
					font-size: 15px;
					line-height: 1.1666666667;
					letter-spacing: 0.009em;
				}
			}
		}
	}
</style>
