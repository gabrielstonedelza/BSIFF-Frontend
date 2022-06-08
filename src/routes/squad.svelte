<script>
	// import cssStyles from '../styles/AboutBsiff.css';
	import { fly } from 'svelte/transition';
	import Florence from '../assets/images/Florence.png';
	import Castro from '../assets/images/Castro.png';
	import David from '../assets/images/David.png';
	import SquadPoster from '../assets/images/YG6A0381.jpg';
	import Philipa from '../assets/images/PHILIPPA .jpeg';
	import Kelvin from '../assets/images/Kelvin.png';
	import Naadede from '../assets/images/Naadede.png';
	import Julie from '../assets/images/JULIET YAA ASANTEWA ASANTE .jpeg';
</script>

<svelte:head>
	<title>BSIFF | The Squad</title>
</svelte:head>

<section in:fly={{ y: 50, duration: 500, delay: 500 }} out:fly={{ duration: 500 }}>
	<!-- <h2 style="text-align:center;padding:20px;">The Squad</h2> -->
	<div class="showcase-container">
		<div class="for-showcase" />
		<div class="overlay" />
		<div class="showcase-content">
			<h2>The Squad</h2>
		</div>
	</div>
	<div class="squad" id="squad-container">
		<div class="squad-main-container">
			<div class="squad-box">
				<div class="for-profile">
					<img src={Julie} alt="" />
				</div>
				<div class="details">
					<h4>JULIET YAA ASANTEWA ASANTE</h4>
					<p>FOUNDING PRESIDENT</p>
				</div>
			</div>
			<div class="squad-box">
				<div class="for-profile">
					<img src={Philipa} alt="" />
				</div>
				<div class="details">
					<h4>PHILIPPA AMA BENTUMA ARTHUR</h4>
					<p>DIRECTOR/FESTIVAL PRODUCER</p>
				</div>
			</div>
			<div class="squad-box">
				<div class="for-profile">
					<img src={Castro} alt="" />
				</div>
				<div class="details">
					<h4>CASTRO</h4>
					<p>TECHNICAL LEAD</p>
				</div>
			</div>
			<div class="squad-box">
				<div class="for-profile">
					<img src={Naadede} alt="" />
				</div>
				<div class="details">
					<h4>NAA DEDE TETTEH</h4>
					<p>PROJECT LEAD, BLACKSTAR MUSIC CONCERT (BMC)</p>
				</div>
			</div>
			<div class="squad-box">
				<div class="for-profile">
					<img src={Florence} alt="" />
				</div>
				<div class="details">
					<h4>FLORENCE M. FOLI</h4>
					<p>CONTENT WRITER</p>
				</div>
			</div>
			<div class="squad-box">
				<div class="for-profile">
					<img src={Kelvin} alt="" />
				</div>
				<div class="details">
					<h4>KELVIN SITTIE</h4>
					<p>SOCIAL MEDIA MANAGER</p>
				</div>
			</div>
			<div class="squad-box">
				<div class="for-profile">
					<img src={David} alt="" />
				</div>
				<div class="details">
					<h4>DAVID NSENKYIRE</h4>
					<p>ASSISTANT</p>
				</div>
			</div>
			<div class="squad-box">
				<div class="for-profile">
					<!-- <img src={Julie} alt=""> -->
				</div>
				<div class="details">
					<h4>TOSIN OJELABI</h4>
					<p>EVENTS MANAGER/SUPERVISOR</p>
				</div>
			</div>
			<div class="squad-box">
				<div class="for-profile">
					<!-- <img src={Julie} alt=""> -->
				</div>
				<div class="details">
					<h4>BEN ADJEI</h4>
					<p>PROJECT LEAD, BSIFF EDU</p>
				</div>
			</div>
		</div>
	</div>
</section>

<style lang="scss">
	.showcase-container {
		width: 100%;
		height: 80vh;
		.for-showcase {
			width: 100%;
			height: 80vh;
			position: absolute;
			background: url('../assets/images/YG6A0381.jpg');
			background-size: cover;
			background-repeat: no-repeat;
			background-position: center;
			background-attachment: fixed;
			z-index: 1;
			object-fit: cover;
		}
		.overlay {
			width: 100%;
			height: 80vh;
			position: absolute;
			background: rgba(0, 0, 0, 0.8);
			z-index: 2;
		}
		.showcase-content {
			position: relative;
			z-index: 3;
			padding-top: 350px;
			h2 {
				display: flex;
				justify-content: center;
				align-items: center;
				font-size: 50px;
				color: #c8a461;
			}
		}
	}

	@media (max-width: 768px) {
		.showcase-container {
			display: none;
		}
	}
	@media (max-width: 500px) {
		.showcase-container {
			display: none;
		}
	}
	#squad-container {
		margin-top: 40px;
		margin-bottom: 20px;
		border-bottom: 1px solid var(--footer-border-color);
		padding: 17px 0 11px;
	}
	.squad {
		margin: 0 auto;
		max-width: 1200px;
		padding: 0 22px;
		padding-left: max(22px, env(safe-area-inset-left));
		padding-right: max(22px, env(safe-area-inset-right));
		.squad-main-container {
			display: flex;
			flex-wrap: wrap;
			gap: 1rem;
			padding: 20px;

			.squad-box {
				width: 300px;
				height: auto;
				display: flex;
				flex-direction: column;
				gap: 0.5rem;
				padding: 20px;

				.for-profile {
					img {
						width: 100%;
						border: solid 2px #c8a461;
						border-radius: 24px;
						height: 100%;
						transition: 1s ease;
					}
					&:hover {
						img {
							transform: scale(1.2);
							background-size: center;
						}
					}
				}
				.details {
					text-align: center;
					h4 {
						padding-top: 10px;
						font-size: 18px;
						font-weight: 600;
						font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
							sans-serif;
					}
				}
			}
		}
	}
	@media (max-width: 768px) {
		.squad {
			.squad-main-container {
				display: flex;
				flex-direction: column;
				justify-content: center;
				align-items: center;
				flex-wrap: nowrap;
				.squad-box {
					.details {
						h4 {
							padding-top: 10px;
							padding-bottom: 10px;
							font-size: 15px;
							font-weight: 600;
							font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
								sans-serif;
						}
						p{
							font-size: 12px;
						}
					}
				}
			}
		}
	}
	@media (max-width: 500px) {
		#squad-container {
			padding: 0;
		}
		.squad {
			.squad-main-container {
				display: flex;
				flex-direction: column;
				justify-content: center;
				align-items: center;
				flex-wrap: nowrap;
				.squad-box {
					.details {
						h4 {
							padding-top: 10px;
							padding-bottom: 10px;
							font-size: 15px;
							font-weight: 600;
							font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
								sans-serif;
						}
						p{
							font-size: 12px;
						}
					}
				}
			}
		}
	}
</style>
