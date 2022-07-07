<script context="module">
	export async function load({ fetch,params }) {
		const res = await fetch(
			`http://127.0.0.1:8000/search_film?search=${params.title}`
		);
		const data = await res.json();
		console.log(params);
	
		if (res.ok) {
			return {
				props: {
					searchedMovie: data
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
		padding-top: 70px;
        display: grid;
        grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
        gap: 1rem;
        height: 20vh;
    }
</style>