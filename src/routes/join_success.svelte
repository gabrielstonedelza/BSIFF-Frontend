<script>
	import { fly } from 'svelte/transition';
	import 'animate.css';
</script>

<section class="container" 
in:fly={{ y: 50, duration: 500, delay: 500 }}
out:fly={{ duration: 500 }}>
	<div class="card">
		<div class="circle">
			<h2 class="animate__animated animate__bounce">Success</h2>
		</div>
		<div class="content">
			<h4>Thank you for joining Bsiff,you are now a member</h4>
		</div>
	</div>
</section>

<style lang="scss">
    section{
        display: flex;
        justify-content: center;
        align-items: center;
        min-height:100vh;
        background: linear-gradient(45deg,#ffaf00,#bb02ff);
    }
	.container {
		// background: linear-gradient(45deg, transparent, transparent, 40%, #e5f403);
		position: relative;
		padding: 20px;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-wrap: wrap;
		margin: 0 auto;
		// &:hover {
		// 	.card {
		// 		filter: blur(20px);
		// 		transform: scale(0.9);
		// 		opacity: 0.5;
		// 	}
		// }

		.card {
			position: relative;
			width: 300px;
			height: 420px;
			background: #d3d3d3;
			margin: 20px;
			border-radius: 20px;
			overflow: hidden;
			box-shadow: 0 15px 25px rgba(0, 0, 0, 0.2);
			transition: 0.5s;
            display:flex;
            justify-content: center;
			// &:hover {
			// 	// filter: blur(0px);
			// 	// transform: scale(1.1);
			// 	// opacity: 1;
			// }

			.circle {
				position: relative;
				width: 100%;
				height: 100%;
				background: #000;
				clip-path: circle(180px at center 0);
				text-align: center;
				h2 {
					color: #fff;
					font-size: 3.5rem;
					padding: 30px 0;
				}
			}
			.content {
				position: absolute;
				bottom: 10px;
				padding: 20px;
				text-align: center;
				h4 {
					color: #c8a461;
					font-size: 1.2rem;
					padding: 20px 0;
				}
				p {
					color: #c8a461;
				}
				a {
					position: relative;
					display: inline-block;
					padding: 10px 20px;
					background: #000;
					color: #fff;
					border-radius: 40px;
					margin-top: 20px;
				}
			}
		}
	}
</style>
