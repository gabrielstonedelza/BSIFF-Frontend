<script>
	let inputValue = '';
	let active = false;
	import { goto } from '$app/navigation';

	function submitSearch() {
		goto('/search/' + inputValue);
	}
</script>

<form on:submit|preventDefault={submitSearch} class="search">
	<input
		on:focus={() => (active = true)}
		on:blur={() => (active = false)}
		type="text"
		id="search-movies"
		name="search-movies"
		placeholder="Search Movies"
		bind:value={inputValue}
		class={active ? 'selected' : ''}
	/>
</form>

<style>
	.search {
		position: relative;
		width: 30%;
		margin: 1rem;
	}

	input {
		width: 100%;
		padding: 12px;
		border: 1px solid #ccc;
		border-radius: 10px;
		box-sizing: border-box;
		resize: vertical;

	}

</style>
