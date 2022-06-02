<script>
	export let movies;
	import MovieCard from '../components/moviecard.svelte';
</script>

<h3>Popular Movies</h3>

<div class="popular-movies">
	{#each movies as movie}
		<MovieCard {movie} />
	{/each}
</div>

<style>
	h3 {
		padding: 0 1rem;
	}
	.popular-movies {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 1rem;
		height: 20vh;
	}
</style>
