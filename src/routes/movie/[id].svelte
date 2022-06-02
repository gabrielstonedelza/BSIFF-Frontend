<script context="module">
	export async function load({ fetch, params }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/${params.id}?api_key=d419dbf4be6123fee9b42ce04438dc53&language=en-US`
		);
		const movieDetail = await res.json();

		if (res.ok) {
			return {
				props: {
					movieDetail
				}
			};
		}
	}
</script>

<script>
	export let movieDetail;
	import { fly } from 'svelte/transition';
</script>

<div
	class="movie-details"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
>
	<div class="img-container">
		<img
			src={'https://image.tmdb.org/t/p/original' + movieDetail.backdrop_path}
			alt={movieDetail.title}
		/>
	</div>
	<div class="txt-container">
		<h1>{movieDetail.title}</h1>
		<p class="overview">
			{movieDetail.overview}
		</p>
		<p>
			<span>Release Date:</span>
			{movieDetail.release_date} <br />
			<span>Budget:</span>
			${movieDetail.budget} <br />
			<span>Rating:</span>
			{movieDetail.vote_average} <br />
			<span>Runtime:</span>
			{movieDetail.runtime} mins
		</p>
	</div>
</div>

<style lang="scss">
	h1 {
		padding: 1rem 0rem 2rem;
	}
	p {
		font-size: 21px;
		line-height: 1.381;
		font-weight: 400;
		letter-spacing: 0.011em;
		font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
			sans-serif;
		color: #86868b;
	}
	.img-container {
		width: 100%;
	}
	img {
		width: 100%;
		border-radius: 1rem;
	}
	.movie-details {
		margin: 2rem 20%;
	}
	span {
		font-weight: bold;
	}
</style>
