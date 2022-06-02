<script>
	let inputValue = '';
	let active = false;
	import { goto } from '$app/navigation';
	import { fly } from 'svelte/transition';

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
	{#if inputValue}
		<button in:fly={{ x: 10, duration: 500 }} out:fly={{ x: 10, duration: 500 }}>Search</button>
	{/if}
</form>

<style>
	.search {
		position: relative;
		width: 30%;
		margin: 1rem;
	}
	button {
		font-size: 0.7rem;
		padding: 0rem 1rem;
		background: rgba(96, 110, 201);
		color: white;
		font-weight: bold;
		border: none;
		position: absolute;
		bottom: 50%;
		right: 0;
		transform: translate(0, 50%);
		height: 100%;
		border-top-right-radius: 10px;
		border-bottom-right-radius: 10px;
		cursor: pointer;
	}
	input {
		width: 100%;
		border: none;
		font-size: 1rem;
		font-family: 'Courier New', Courier, monospace;
		outline: none;
		color: rgba(255, 255, 255);
		padding: 0.5rem 0.1rem;
		transition: background 0.75s ease-out;
		font-weight: bold;
		background-color: rgba(63, 63, 63);
		border-radius: 10px;
		padding: 1rem;
	}
	input.selected {
		background: rgb(0, 0, 0);
	}
</style>
