<script>
	import { fly } from 'svelte/transition';
</script>

<section
	class="ticket-container"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
>
	<br />

	<div class="theater-container">
		<div
			class="join-bsiff-container"
			style="background:linear-gradient(0deg, rgba(15,3,48,0.9) 0%, rgba(76,2,115,0.7) 80%), url(https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.Ck7YKcvaw4FA-Ba886LxjAHaDt%26pid%3DApi&f=1) no-repeat;background-size: cover;margin-top:-10px;background-position:center;width:100%;"
		>
			<div class="tickets-contents">
				<!-- now open and deadline -->
				<h4>The ticket office of the BSIFF 2022 is now opened.</h4>
				<span class="middle-line" />
				<div class="other-notice">
					<p>
						Discover the ticket and PASS for anoter edition of the Black Star International Film
						Festival which will take place from September 25 to September 25 2022
					</p>
				</div>
			</div>
			<!-- ticket packages -->
		</div>
		<div class="container">
			<div class="card">
				<div class="circle">
					<h2>90GH</h2>
				</div>
				<div class="content">
					<h4>Small Pass</h4>
					<p>
						Access to all the Festival's screenings (excepted to the Opening and Closing Ceremony) 1
						Totebag + 1 catalog
					</p>
					<a href="https://github.com/" target="_blank">Buy Now</a>
				</div>
			</div>
			<div class="card">
				<div class="circle">
					<h2>150GH</h2>
				</div>
				<div class="content">
					<h4>Big Pass</h4>
					<p>
						Access to all the Festival's screenings Access to the Opening Ceremony Access to the
						Closing Ceremony) 1 Totebag + 1 catalog
					</p>
					<a href="https://github.com/" target="_blank">Buy Now</a>
				</div>
			</div>
			<div class="card">
				<div class="circle">
					<h2>300GH</h2>
				</div>
				<div class="content">
					<h4>Opening & Closing</h4>
					<p>
						The Opening film of the BRIFF 2022 Coupez! (Final Cut) by director Michel Hazanavicius
						will be screened in the presence of the film crew
					</p>
					<a href="https://github.com/" target="_blank">Buy Now</a>
				</div>
			</div>
			<div class="card">
				<div class="circle">
					<h2>700GH</h2>
				</div>
				<div class="content">
					<h4>SCREENING TICKET</h4>
					<p>Tickets are valid for for one screening of your choice</p>
					<a href="https://github.com/" target="_blank">Buy Now</a>
				</div>
			</div>
		</div>
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
	.ticket-container {
		.theater-container {
			.tickets-contents {
				padding-top: 250px;
				display: flex;
				justify-content: center;
				align-items: center;
				flex-direction: column;
				gap: 1rem;
				width: 70%;
				margin: 0 auto;
				text-align: center;
				color: #c8a461;

				h4 {
					font-size: 40px;
				}
				p {
					font-size: 25px;
					line-height: 1.5;
					margin-bottom: 60px;
				}
			}
		}
		// for container
		.container {
			position: relative;
			padding: 20px;
			display: flex;
			justify-content: center;
			align-items: center;
			flex-wrap: wrap;
			margin: 0 auto;
			&:hover {
				.card {
					filter: blur(20px);
					transform: scale(0.9);
					opacity: 0.5;
				}
			}

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
				&:hover {
					filter: blur(0px);
					transform: scale(1.1);
					opacity: 1;
				}

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
	}
	.container .card:nth-child(1) .circle,
	.container .card:nth-child(1) .content a {
		background: #ffaf00;
	}
	.container .card:nth-child(2) .circle,
	.container .card:nth-child(2) .content a {
		background: #da2268;
	}
	.container .card:nth-child(3) .circle,
	.container .card:nth-child(3) .content a {
		background: #bb02ff;
	}

	// media query
	@media (max-width: 991px) {
		.ticket-container {
			.theater-container {
				.tickets-contents {
					padding-top: 100px;
					h4 {
						font-size: 30px;
					}
					p {
						font-size: 20px;
						line-height: 1.5;
						margin-bottom: 60px;
					}
				}
			}
            .container{
                .card{
                    .circle{
                        h2{
                           font-size: 2.5rem;
                        }
                    }
                }
            }
		}
	}

	@media (max-width: 992px) {
		.ticket-container {
			.theater-container {
				.tickets-contents {
					padding-top: 100px;
					h4 {
						font-size: 30px;
					}
					p {
						font-size: 15px;
						line-height: 1.5;
						margin-bottom: 30px;
					}
				}
			}
		}
	}
    @media (max-width: 688px) {
		.ticket-container {
			.theater-container {
				.tickets-contents {
					padding-top: 100px;
					h4 {
						font-size: 20px;
					}
					p {
						font-size: 10px;
						line-height: 1.5;
						margin-bottom: 30px;
					}
				}
			}
		}
	}
</style>
