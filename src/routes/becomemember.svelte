<script>
	import { fly } from 'svelte/transition';
</script>

<svelte:head>
	<title>BSIFF | Join BSIFF</title>
</svelte:head>

<section
	class="join-bsiff"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
>
	<div class="join-bsiff-container" style="background:linear-gradient(0deg, rgba(15,3,48,0.9) 0%, rgba(76,2,115,0.7) 80%), url(https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.Ck7YKcvaw4FA-Ba886LxjAHaDt%26pid%3DApi&f=1) no-repeat;background-size: cover;margin-top:-10px;background-position:center;width:100%;">
		<div class="jbsiff-contents">
			<br />
			<br />
			<br />
			<br />
			<h1>Join BSIFF</h1>
			<h2 class="sub-join-text">
				Enjoy free films, exclusive pre-sales, priority service, and so much more!
			</h2>
			<a href="">Join Or Renew</a>
			<br />
			<br />
			<br />
		</div>
	</div>
</section>

<style lang="scss">
	.join-bsiff {
		padding-top: 30px;
		.join-bsiff-container {
			width: 100%;
			// height: 80vh;
			transition: 1s ease;

			.jbsiff-contents {
				display: flex;
				flex-direction: column;
				gap: 1rem;
				justify-content: center;
				align-items: center;
				padding: 20px;
				h1 {
					color: #c8a461;
					font-size: 64px;
					font-weight: 500;
					letter-spacing: 0;
				}
				h2 {
					color: #c8a461;
					font-size: 24px;
					font-weight: 500;
					padding: 10px;
				}
				a {
					padding-left: 20px;
					padding-right: 20px;
					padding-top: 10px;
					padding-bottom: 10px;
					background-color: #c8a461;
					color: #000;
					border-radius: 24px;
					margin-left: 40px;
				}
			}
		}
	}

	@media (max-width: 768px) {
		*{
			box-sizing: border-box;
		}
		.join-bsiff {
			.join-bsiff-container {
				.jbsiff-contents {
					position: relative;
					z-index: 3;
					display: flex;
					flex-direction: column;
					gap: 1rem;
					justify-content: center;
					align-items: center;
					// padding-top: 20px;
					h1 {
						color: #c8a461;
						font-size: 44px;
						font-weight: 500;
						margin: 1em auto 0 auto;
						letter-spacing: 0;
					}
					h2 {
						color: #c8a461;
						font-size: 20px;
						font-weight: 500;
						// margin: 1em auto 0 auto;
						letter-spacing: 0;
						padding: 20px;
					}
				}
			}
		}
	}
	@media (max-width: 500px) {
		.join-bsiff {
			.join-bsiff-container {
				.jbsiff-contents {
					position: relative;
					z-index: 3;
					display: flex;
					flex-direction: column;
					gap: 1rem;
					justify-content: center;
					align-items: center;
					h1 {
						color: #c8a461;
						font-size: 24px;
						font-weight: 500;

					}
					h2 {
						color: #c8a461;
						font-size: 15px;
						font-weight: 500;
						padding: 20px;
					}
				}
			}
		}
	}
</style>
