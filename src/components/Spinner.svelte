<section class="loader-container">
	<div class="loader" />
</section>

<style lang="scss">
	.loader-container {
		top: 0;
		position: fixed;
		width: 100%;
		height: 100%;
		background-color: #000;
		z-index: 2000;
		display: flex;
		justify-content: center;
		align-items: center;

		.loader {
			position: relative;
			width: 150px;
			height: 150px;
			border-radius: 50%;
            background: linear-gradient(45deg,transparent,transparent, 40%,#e5f403);
			animation: animate 2s linear infinite;

			&:before {
				content: '';
				position: absolute;
				top: 6px;
				left: 6px;
				right: 6px;
				bottom: 6px;
				background: #000;
				border-radius: 50%;
				z-index: 1000;
			}
			&:after {
				content: '';
				position: absolute;
				top: 0px;
				left: 0px;
				right: 0px;
				bottom: 0px;
                background: linear-gradient(45deg,transparent,transparent, 40%,#e5f403);
				border-radius: 50%;
				z-index: 1000;
				z-index: 1;
				filter: blur(30px);
			}
		}
	}

	@keyframes animate {
		0% {
			transform: rotate(0deg);
			filter: hue-rotate(0deg);
		}
		100% {
			transform: rotate(360deg);
			filter: hue-rotate(360deg);
		}
	}
</style>
