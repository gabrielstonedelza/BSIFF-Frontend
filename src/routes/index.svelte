<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			'https://api.themoviedb.org/3/movie/popular?api_key=d419dbf4be6123fee9b42ce04438dc53&language=en-US&page=1'
		);
		const data = await res.json();

		if (res.ok) {
			return {
				props: {
					popular: data.results
				}
			};
		}
	}
</script>

<script>
	import Showcase from '../components/showcase.svelte';
	import RamdomMovies from '../components/random.svelte';
	import SearchMovies from '../components/SearchMovies.svelte';
	import SocialMovies from '../components/SocialMedia.svelte';
	export let popular;
	import { fly } from 'svelte/transition';
</script>

<svelte:head>
	<title>BSIFF | Home</title>
</svelte:head>

<section in:fly={{ y: 50, duration: 500, delay: 500 }} out:fly={{ duration: 500 }}>
	<SocialMovies />
	<Showcase />
	<SearchMovies />
	<RamdomMovies movies={popular} />
</section>

