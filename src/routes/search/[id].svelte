<script context="module">
	export async function load({ fetch,params }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/search/movie?api_key=d419dbf4be6123fee9b42ce04438dc53&language=en-US&query=${params.id}&page=1&include_adult=false`
		);
		const data = await res.json();
	
		if (res.ok) {
			return {
				props: {
					searchedMovie: data.results
				}
			};
		}
	}
</script>

<script>
    import MovieCard from '../../components/moviecard.svelte';
    export let searchedMovie;
</script>

<div class="searched-movies">
    {#each searchedMovie as movie}
        <MovieCard {movie}/>
    {/each}
</div>

<style>
    .searched-movies{
        display: grid;
        grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
        gap: 1rem;
        height: 20vh;
    }
</style>