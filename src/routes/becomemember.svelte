<script>
	import { fly } from 'svelte/transition';
	import axios from 'axios';
	import { goto } from '$app/navigation';

	let hasErros = false;
	let isSucceeded = false;
	let notValidEmail = false;
	let username = '';
	let name = '';
	let email = '';
	let password1 = '';
	let password2 = '';
	let errorMessage = '';
	let successMessage = '';
	let nameError = '';
	let hasNameError = false;
	let userNameError = '';
	let hasUserNameError = false;
	let emailError = '';
	let hasEmailError = false;
	let passwordError = '';
	let hasPasswordError = false;


	const handleSubmitForm = async (e) => {
		const apiUrl = 'http://127.0.0.1:8000/auth/users/';
		axios({
			method: 'POST',
			url: apiUrl,
			data: {
				username: username,
				full_name: name,
				email: email,
				password: password1,
				re_password: password2
			},
			headers: { 'Content-Type': 'multipart/form-data' }
		})
			.then(function (response) {
				goto('/login/');

			})
			.catch((error) => {
				if (error.response) {
					if (error.response.data['username']) {
						hasUserNameError = true;
						userNameError = `Sorry 😢,${error.response.data['username']}`;
					}
					if (error.response.data['full_name']) {
						hasNameError = true;
						nameError = `Sorry 😢,${error.response.data['full_name']}`;
					}
				
					if (error.response.data['email']) {
						hasEmailError = true;
						emailError = `Sorry 😢,${error.response.data['email']}`;
					}
					if (error.response.data['password']) {
						hasPasswordError = true;
						passwordError = `Sorry 😢,${error.response.data['password']}`;
					}
					
				}
				console.log(error.response)
				
			});
	};
</script>

<svelte:head>
	<title>BSIFF | Join BSIFF</title>
</svelte:head>

<section
	class="join-bsiff"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
>
	<div
		class="join-bsiff-container"
		style="background:linear-gradient(0deg, rgba(15,3,48,0.9) 0%, rgba(76,2,115,0.7) 80%), url(https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.Ck7YKcvaw4FA-Ba886LxjAHaDt%26pid%3DApi&f=1) no-repeat;background-size: cover;margin-top:-10px;background-position:center;width:100%;"
	>
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
	<!-- benefits -->

	<div class="benefits" />
	<!-- join form -->
	<div class="join-now">
		<form class="form" on:submit|preventDefault={handleSubmitForm}>
			<div class="heading">
				<h1 class="form__title">Join Now</h1>
			</div>

			<div class="form__group">
				<input
					type="text"
					id="name"
					class="form__input"
					placeholder=""
					autocomplete="off"
					bind:value={username}
					required
				/>
				<label for="name" class="form__label">Username</label>
			</div>
			{#if hasUserNameError}
				<div class="full_error">
					<p>{userNameError}</p>
				</div>
			{/if}
			<div class="form__group">
				<input
					type="text"
					id="name"
					class="form__input"
					placeholder=""
					autocomplete="off"
					bind:value={name}
					required
				/>
				<label for="name" class="form__label">Name</label>
			</div>
			{#if hasNameError}
				<div class="full_error">
					<p>{nameError}</p>
				</div>
			{/if}
			<div class="form__group">
				<input
					type="text"
					id="email"
					class="form__input"
					placeholder=""
					autocomplete="off"
					bind:value={email}
					required
				/>
				<label for="email" class="form__label">Email</label>
			</div>
			{#if hasEmailError}
				<div class="full_error">
					<p>{emailError}</p>
				</div>
			{/if}

			<div class="form__group">
				<input
					type="password"
					id="password"
					class="form__input"
					placeholder=""
					autocomplete="off"
					bind:value={password1}
					required
				/>
				<label for="password" class="form__label">Password</label>
			</div>
			{#if hasPasswordError}
				<div class="full_error">
					<p>{passwordError}</p>
				</div>
			{/if}
			<button class="form__button">Join</button>
		</form>
	</div>
</section>

<style lang="scss">
	$clr-primary: #18ffff;
	$clr-primary-light: #adffff;
	$clr-primary-dark: #091034;
	$clr-gray100: #f9fbff;
	$clr-gray150: #f4f6fb;
	$clr-gray200: #eef1f6;
	$clr-gray300: #e1e5ee;
	$clr-gray400: #767b91;
	$clr-gray500: #4f546c;
	$clr-gray600: #2a324b;
	$clr-bg: #060b23;
	$radius: 1rem;

	*,
	*::before,
	*::after {
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}
	.join-now {
		font-family: monospace;
		font-weight: 500;
		// height: 100vh;
		display: grid;
		justify-content: center;
		align-items: center;
		color: #c8a461;
		padding: 20px;


		.form {
			width: 60rem;
			padding: 2rem;
			border-radius: $radius;
			background-color: $clr-bg;
			.full_error {
				opacity: 0;
				-moz-animation: cssAnimation 0.5s;
				/* Firefox */
				-webkit-animation: cssAnimation 0.5s;
				/* Safari and Chrome */
				-o-animation: cssAnimation 0.5s;
				/* Opera */
				animation: cssAnimation 0.5s;
				-webkit-animation-fill-mode: forwards;
				animation-fill-mode: forwards;
				p {
					display:flex;
					align-items: center;
					padding: 10px;
					color: red;
				}
			}

			.heading {
				display: flex;
				gap: 1rem;
				align-items: center;
				transition: 1s ease;

			}

			.form__title {
				margin-bottom: 1rem;
			}

			.form__group {
				position: relative;
				height: 3rem;
				margin-bottom: 1.5rem;
				// width: 100%;
				input {
					width: 100%;
					height: 100%;
					border: 2px solid $clr-primary;
					border-radius: 0.5rem;
					outline: none;
					padding: 1.25rem;
					background: none;
					color: inherit;
					transition: 1s ease;
					&:hover {
						border-color: $clr-gray100;
					}
					&:focus {
						border-color: white;
					}
				}

				label {
					position: absolute;
					left: 1rem;
					top: 0.9rem;
					padding: 0 0.5rem;
					transition: top 200ms ease-in, left 200ms ease-in, font-size 200ms ease-in;
					background-color: $clr-bg;
				}
			}
			button {
				display: black;
				margin-left: auto;
				padding: 0.75rem 2rem;
				background: $clr-primary-dark;
				border-radius: 0.5rem;
				outline: none;
				border: none;
				cursor: pointer;
				transition: 1s ease-in;
				color: #c8a461;
				&:hover {
					background-color: $clr-primary;
				}
			}

			.form__input:focus ~ .form__label,
			.form__input:not(:placeholder-shown).form__input:not(:focus) ~ .form__label {
				top: -0.5rem;
				left: 0.8rem;
				font-size: 0.8rem;
			}
		}
	}
	.error-borders{
		.form__group{
			input{
				border-color: red;
			}
		}
	}
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
	@media (max-width: 991px) {
		.join-now {
			padding: 40px;
			.form {
				width: 45rem;
				padding: 20px;
			}
		}
	}

	@media (max-width: 768px) {
		* {
			box-sizing: border-box;
		}
		.join-bsiff {
			.join-now{
				padding: 40px;
			.form {
				width: 35rem;
				padding: 20px;
			}
			}
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
			.join-now{
				padding: 40px;
			.form {
				width: 25rem;
				padding: 20px;
			}
			}
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
	@keyframes cssAnimation {
		99% {
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}
	@-webkit-keyframes cssAnimation {
		99% {
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}
</style>
