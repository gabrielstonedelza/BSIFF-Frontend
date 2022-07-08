
<script context="module">
	export async function load({ fetch }) {
		const res = await fetch('https://rvci.xyz/get_gallery/');
		const gallery = await res.json();
	

		if (res.ok) {
			return {
				props: {
					gallery
				}
			};
		}
	}
</script>
<script>
	import { fly } from 'svelte/transition';


	let imageModal = "";
	let openModalImage = false;
	
	export let gallery;

	function closeModal() {
		openModalImage = false;
	}
	function openModal(src) {
		openModalImage = true;
		imageModal = src;
		// return src;
	}
</script>

<svelte:head>
	<title>BSIFF | Gallery</title>
</svelte:head>

<section
	class="gallery-container"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
>
	{#if openModalImage}
		<div class="modal">
			<button on:click={closeModal}>x</button>
			<div class="modal-content">
				<img src={imageModal} alt="" />
			</div>
		</div>
	{/if}
	<br />
	<br />
	<br />
	<div class="gallery-box">
		{#each gallery as pic}
			<div class="box">
				<img src={pic.get_image} alt="" on:click={(e) => openModal(pic.get_image)} />
			</div>
		{/each}
	</div>
</section>

<style lang="scss">
	*,
	*::before,
	*::after {
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}
	
	.modal {
		width: 100%;
		background-color: rgba(0, 0, 0, 0.829);
		position: fixed;
		z-index: 1000;
		top: 0;
		left: 0;
		bottom: 0;
		right: 0;
		overflow: hidden;
		
		button {
			padding: 20px;
			border: none;
			font-size: 30px;
			background: none;
			color: white;
			float: right;
			padding-right: 30px;
			cursor: pointer;
		}
		.modal-content {
			transition: 1s ease;
			padding: 20px;
			display: flex;
			justify-content: center;
			align-items: center;
			img {
				max-width: 80%;
				height: auto;
				border-radius: 24px;
				// max-height: 100%;
			}
		}
	}
	.gallery-container {
		max-width: 1200px;
		margin: 0 auto;

		.gallery-box {
			display: grid;
			grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
			gap: 1rem;
			padding: 20px;
			cursor: pointer;
			.box {
				img {
					width: 100%;
					height: 100%;
					object-fit: cover;
					border-radius: 15px;
					// border: solid 2px #c8a461;
					box-shadow: 0 3px 10px rgb(0 0 0 / 0.2);
				}
			}
		}
	}
	// media query
	@media(max-width:768px){
		.modal{
			display: none;
		}
	}
	@media(max-width:500px){
		.modal{
			display: none;
		}
	}
</style>
