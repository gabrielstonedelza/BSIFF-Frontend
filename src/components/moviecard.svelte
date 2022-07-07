<script>
	export let movie;
</script>

<div class="movie-card">
	<a sveltekit:prefetch sveltekit:noscroll href={'/movie/' + movie.slug}>
		<img src={movie.get_movie_poster} alt={movie.title} />
	</a>
	<div class="description">
		<h2>{movie.title}</h2>
		<!-- <p>{movie.release_date}</p> -->
	</div>
</div>

<style>
	img {
		width: 100%;
		height: 30vh;
		object-fit: cover;
		border-radius: 1rem;
		margin-bottom: 1rem;
	}
	h2 {
		font-size: 0.9rem;
	}
	.description {
		height: 5vh;
	}
	p {
		font-size: 0.7rem;
	}
	.movie-card {
		width:270px;
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		padding: 1rem;
	}
</style>
