<script context="module">
	export async function load({ fetch }) {
		const res = await fetch('https://rvci.xyz/get_all_submitted_film/', {
			headers: {
				'content-type': 'application/json',
				accept: 'application/json'
			}
		});
		const data = await res.json();

		if (res.ok) {
			return {
				props: {
					selectedFilm: data
				}
			};
		} else {
			console.error;
		}
	}
</script>

<script>
	import Showcase from '../components/showcase.svelte';
	import RamdomMovies from '../components/random.svelte';
	import SearchMovies from '../components/SearchMovies.svelte';
	import SocialMovies from '../components/SocialMedia.svelte';
	export let selectedFilm;
	import { fly } from 'svelte/transition';
</script>

<svelte:head>
	<title>BSIFF | Home</title>
</svelte:head>

<section in:fly={{ y: 50, duration: 500, delay: 500 }} out:fly={{ duration: 500 }}>
	<SocialMovies />
	<Showcase />
	<SearchMovies />
	<RamdomMovies movies={selectedFilm} />
</section>
