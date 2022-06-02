<script>
	export let movies;
	import TrendingCard from '../components/TrendingCard.svelte';
</script>

<h3>Official Selection</h3>

<div class="popular-movies">
	{#each movies as movie}
		<TrendingCard {movie} />
	{/each}
</div>

<style>
	h3 {
		text-align: center;
		padding-top: 50px;
		padding-bottom: 20px;
		font-size: 28px;
		line-height: 1.08349;
		font-weight: 600;
		letter-spacing: -0.003em;
		font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
			sans-serif;
	}
	.popular-movies {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 1rem;
		height: 20vh;
	}
</style>
