<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			'https://api.themoviedb.org/3/trending/all/day?api_key=d419dbf4be6123fee9b42ce04438dc53'
		);
		const data = await res.json();

		if (res.ok) {
			return {
				props: {
					trending: data.results
				}
			};
		}
	}
</script>

<script>
	// import cssStyles from '../styles/AboutBsiff.css';
	import { fly } from 'svelte/transition';
	import Trendind from '../components/Trending.svelte'
	export let trending
</script>

<svelte:head>
	<title>BSIFF | Official Selection</title>
</svelte:head>

<section
	class="officialselection"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
>
	
	<Trendind movies={trending} />
</section>

<style lang="scss">
</style>
