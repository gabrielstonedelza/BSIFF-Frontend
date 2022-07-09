<script>
	import { fly } from 'svelte/transition';
	import Location from '../assets/images/icons/location-1.png';
	import Email from '../assets/images/icons/mail.png';
	import Phone from '../assets/images/icons/phone-call.png';
	import Facebook from '../assets/images/icons/facebook.png';
	import Instagram from '../assets/images/icons/instagram.png';
	import Twitter from '../assets/images/icons/twitter.png';
	import Youtube from '../assets/images/icons/youtube.png';
	import axios from 'axios';
	import { goto } from '$app/navigation';

	let first_name = '';
	let last_name = '';
	let phone = '';
	let email = '';
	let message = '';
	let hasErrors = '';
	let hasEmailError = false;
	let emailError = '';
	let hasPhoneError = false;
	let phoneError = '';
	let isPosting = true;

	const handleErrorContainer = () => {
		hasErrors = false;
	};

	const handleSubmitFile = async () => {
		const apiUrl = 'https://rvci.xyz/contact_us/';
		axios({
			method: 'POST',
			url: apiUrl,
			data: {
				first_name: first_name,
				last_name: last_name,
				email: email,
				mobile_num: phone,
				message: message
			},
			headers: { 'Content-Type': 'multipart/form-data' }
		})
			.then((response) => {
				goto('/success');
			})
			.catch((error) => {
				if (error.response) {
					console.log(error.response);
					if (error.response.data['email']) {
						hasErrors = true;
						hasEmailError = true;
						emailError = `${error.response.data['email']}`;
					}
					if (!error.response.data['email']) {
						hasEmailError = false;
						emailError = '';
					}
					if (error.response.data['mobile_num']) {
						hasErrors = true;
						hasPhoneError = true;
						phoneError = `${error.response.data['mobile_num']}`;
					}
					if (!error.response.data['mobile_num']) {
						hasPhoneError = false;
						phoneError = '';
					}
				}
			});
	};
</script>

<svelte:head>
	<title>BSIFF | Contact Us</title>
</svelte:head>

<section
	class="my-contact-form"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
>
	<div class="container">
		<div class="contactInfo">
			
			<div>
				<h2>Contact Information</h2>
				<ul class="info">
					<li>
						<span>
							<img src={Location} alt="" />
						</span>
						<span>Accra-Ghana</span>
					</li>
					<li>
						<span>
							<img src={Email} alt="" />
						</span>
						<span>info@blackstarinternational<br />filmfestival.org</span>
					</li>
					<li>
						<span>
							<img src={Phone} alt="" />
						</span>
						<span>
							+233 030 293 5303
							<br />
							+233 506481853
						</span>
					</li>
				</ul>
			</div>
			<ul class="sci">
				<li>
					<a href="https://web.facebook.com/BSIFF.org" target="_blank">
						<img src={Facebook} alt="facebook logo" />
					</a>
				</li>
				<li>
					<a href="https://www.youtube.com/watch?v=IGSLw-seetE" target="_blank">
						<img src={Instagram} alt="instagram logo" />
					</a>
				</li>
				<li>
					<a href="https://twitter.com/theBSIFF?s=08" target="_blank">
						<img src={Twitter} alt="twitter logo" />
					</a>
				</li>
				<li>
					<a href="https://www.youtube.com/watch?v=IGSLw-seetE" target="_blank">
						<img src={Youtube} alt="youtube logo" />
					</a>
				</li>
			</ul>
		</div>
		<form class="contactForm" on:submit|preventDefault={handleSubmitFile}>
			{#if hasErrors}
				<div class="error-container">
					<div class="error-box">
						<div class="errors">
							{#if hasEmailError}
								<h3>Email: {emailError}</h3>
							{/if}
							{#if hasPhoneError}
								<h3>Mobile Number: {phoneError}</h3>
							{/if}
						</div>
						<p on:click={handleErrorContainer}>X</p>
					</div>
				</div>
			{/if}
			<h2>Message Us</h2>
			<div class="formBox">
				<div class="inputBox w50">
					<input
						type="text"
						id="first_name"
						class="form__input"
						placeholder=""
						autocomplete="off"
						bind:value={first_name}
						required
					/>
					<span>First Name</span>
				</div>
				<div class="inputBox w50">
					<input
						id="last_name"
						class="form__input"
						placeholder=""
						autocomplete="off"
						bind:value={last_name}
						required
					/>
					<span>Last Name</span>
				</div>
				<div class="inputBox w50">
					<input
						id="email"
						class="form__input"
						placeholder=""
						autocomplete="off"
						bind:value={email}
						required
					/>
					<span>Email</span>
				</div>
				
				<div class="inputBox w100">
					<textarea required bind:value={message} />
					<span>Write Your Message</span>
				</div>
				<div class="inputBox w100">
					<input type="submit" value="Send" />
				</div>
			</div>
		</form>
	</div>
</section>

<style lang="scss">
	* {
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}
	section {
		.error-container {
			position: fixed;
			margin-top: 5px;
			padding: 10px;
			z-index: 1000;
			background: rgba(0, 0, 0, 0.8);
			border-top-right-radius: 20px;
			border-bottom-right-radius: 20px;
			transition: 2s ease;
			.error-box {
				display: flex;
				gap: 1rem;
				.errors {
					h3 {
						color: red;
						font-size: 15px;
					}
				}
				p {
					color: white;
					font-size: 25px;
					cursor: pointer;
					font-weight: bold;
				}
			}
		}
		display: flex;
		justify-content: center;
		align-items: center;
		// background-color: #095a55;
		min-height: 100vh;

		// &::before {
		// 	content: '';
		// 	position: absolute;
		// 	top: 0;
		// 	left: 0;
		// 	width: 50%;
		// 	height: 100%;
		// 	background-color: #fff38e;
		// }
		.container {
			position: relative;
			min-width: 1100px;
			min-height: 550px;
			display: flex;
			z-index: 1000;
			// background-color: #fff;

			.contactInfo {
				position: absolute;
				top: 40px;
				width: 350px;
				height: calc(100% - 80px);
				background-color: #060b23;
				z-index: 1;
				padding: 40px;
				display: flex;
				justify-content: center;
				flex-direction: column;
				justify-content: space-between;
				box-shadow: 0 20px 25px rgba(0, 0, 0, 0.15);
				border-radius: 24px;
				h2 {
					color: #c8a461;
					font-size: 24px;
					font-weight: 500;
				}
				ul.info {
					position: relative;
					margin: 20px 0;
					li {
						position: relative;
						list-style: none;
						display: flex;
						margin: 20px 0;
						cursor: pointer;
						align-items: flex-start;
						span:nth-child(1) {
							width: 30px;
							min-width: 30px;
							img {
								max-width: 100%;
								filter: invert(1);
							}
						}
						span:nth-child(2) {
							color: #c8a461;
							margin-left: 10px;
							font-weight: 300;
						}
					}
				}
				ul.sci {
					position: relative;
					display: flex;
					li {
						list-style: none;
						margin-left: 15px;
						a {
							img {
								width: 30px;
								height: 30px;
							}
						}
					}
				}
			}
			.contactForm {
				position: absolute;
				padding: 70px 50px;
				padding-left: 250px;
				margin-left: 150px;
				width: calc(100% - 150px);
				height: 100%;
				background-color: #ffffffeb;
				box-shadow: 0 50px 50px rgba(0, 0, 0, 0.25);
				border-radius: 24px;
				h2 {
					color: #c8a461;
					font-size: 24px;
					font-weight: 500;
				}
				.formBox {
					position: relative;
					display: flex;
					justify-content: space-between;
					flex-wrap: wrap;
					padding-top: 30px;
					.inputBox {
						position: relative;
						margin-bottom: 35px;
						input,
						textarea {
							width: 100%;
							resize: none;
							padding: 5px 0;
							font-size: 18px;
							color: #c8a461;
							border: none;
							outline: none;
							border-bottom: 1px solid #777;
						}
						textarea {
							height: 120px;
						}
						span {
							position: absolute;
							left: 0;
							padding: 5px 0;
							pointer-events: none;
							font-size: 18px;
							font-weight: 300;
							transition: 0.3s;
							color: #c8a461;
						}

						input:focus ~ span,
						input:valid ~ span {
							transform: translateY(-20px);
							font-size: 12px;
							font-weight: 400;
							letter-spacing: 1px;
							color: #c8a461;
							font-weight: 500;
						}
						textarea:focus ~ span,
						textarea:valid ~ span {
							transform: translateY(-20px);
							font-size: 12px;
							font-weight: 400;
							letter-spacing: 1px;
							color: #c8a461;
							font-weight: 500;
						}
						input[type='submit'] {
							position: relative;
							cursor: pointer;
							background-color: #c8a461;
							color: #000;
							border: none;
							max-width: 150px;
							padding: 12px;
							border-radius: 24px;
							&:hover {
								background-color: #0d948b;
							}
						}
					}
					.w50 {
						width: 47%;
					}
					.w100 {
						width: 100%;
					}
				}
			}
		}
	}

	// media query
	@media (max-width: 1200px) {
		section {
			.container {
				width: 90%;
				min-width: auto;
				margin: 20px;
				box-shadow: 0 20px 50px rgba(0, 0, 0, 0.2);
				.contactInfo {
					top: 0;
					height: 550px;
					position: relative;
					box-shadow: none;
				}
				.contactForm {
					position: relative;
					width: calc(100% - 350px);
					padding-left: 0;
					margin-left: 0;
					padding: 40px;
					height: 550px;
					box-shadow: none;
					border-radius: none;
				}
			}
		}
	}
	@media (max-width: 991px) {
		section {
			padding: 20px;

			.container {
				z-index: 2;
				padding: 20px;
				display: flex;
				flex-direction: column-reverse;

				.contactForm {
					width: 100%;
					height: auto;
					border-radius: 0;
					padding-top: 20px;
				}
				.contactInfo {
					border-radius: 0;
					width: 100%;
					height: auto;
					flex-direction: row;
					ul.sci {
						position: relative;
						display: flex;
						justify-content: center;
						align-items: center;
					}
				}
			}
		}
	}
	@media (max-width: 600px) {
		section {
			.container {
				z-index: 2;
				.contactForm {
					padding: 25px;

					.formBox {
						.inputBox.w50 {
							width: 100%;
						}
					}
				}
				.contactInfo {
					padding: 25px;
					flex-direction: column;
					align-items: flex-start;
					border-radius: 0;
					ul.sci {
						margin-top: 40px;
					}
				}
			}
		}
	}
</style>
