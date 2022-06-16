<script>
	import { fly } from 'svelte/transition';
	import image1 from '../assets/images/gallery/IMG_0015-34.jpeg';
	import image2 from '../assets/images/gallery/IMG_6093.jpeg';
	import image3 from '../assets/images/gallery/IMG_9046.jpg';
	import image4 from '../assets/images/gallery/IMG_9067.jpg';
	import image5 from '../assets/images/gallery/IMG_9072.jpg';
	import image6 from '../assets/images/gallery/JOIN BSIFF 2.jpeg';
	import image7 from '../assets/images/gallery/JOIN BSIFF.jpg';
	import image8 from '../assets/images/gallery/OFF PEAK 1.jpeg';
	import image9 from '../assets/images/gallery/OFF PEAK 2.jpeg';
	import image10 from '../assets/images/gallery/OFF PEAK 3.jpeg';
	import image11 from '../assets/images/gallery/untitled-1373.jpeg';
	import image12 from '../assets/images/gallery/untitled-1391.jpeg';
	import image13 from '../assets/images/gallery/untitled-1427.jpeg';
	import image14 from '../assets/images/gallery/untitled-1447.jpeg';
	import image15 from '../assets/images/gallery/untitled-2024.jpeg';
	import image16 from '../assets/images/gallery/untitled-2146.jpeg';
	import image17 from '../assets/images/gallery/untitled-2245.jpeg';
	import image18 from '../assets/images/gallery/VOLUNTEER WITH US.jpg';
	import image19 from '../assets/images/gallery/WHO WE ARE.jpeg';
	import image20 from '../assets/images/gallery/YG6A0451.jpg';

	let imageModal = "";
	let openModalImage = false;
	let pics = [
		image1,
		image2,
		image3,
		image4,
		image5,
		image6,
		image7,
		image8,
		image9,
		image10,
		image11,
		image12,
		image13,
		image14,
		image15,
		image16,
		image17,
		image18,
		image19,
		image20
	];

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
		{#each pics as pic}
			<div class="box">
				<img src={pic} alt="" on:click={(e) => openModal(pic)} />
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
		transition: 1s ease;
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
	@media(max-width:500px){
		.modal{
			display: none;
		}
	}
</style>
