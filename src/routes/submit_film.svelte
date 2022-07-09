<script>
	import { fly } from 'svelte/transition';
	import axios from 'axios';
	import { goto } from '$app/navigation';
	let category;
	let title;
	let poster;
	let description;
	let language;
	let genre;
	let country;
	let directors;
	let producers;
	let writers;
	let key_casts;
	let submittersBio;
	let trailer;
	let duration;
	let movieLink;
	// error messages
	let hasErrors = false;
	let posterError = '';
	let trailerError = '';
	let movie_linkError = '';
	let hasPosterError = false;
	let hasTrailerError = false;
	let hasmovie_linkError = false;

	const checkFile = (e) => {
		poster = e.target.files[0];
	};

	const checkTrailer = (e) => {
		trailer = e.target.files[0];
	};

	const handleErrorContainer = () => {
		hasErrors = false;
	};

	const handleSubmitFile = async () => {
		const apiUrl = 'https://rvci.xyz/submit_film/';
		axios({
			method: 'POST',
			url: apiUrl,
			data: {
				title: title,
				category: category,
				poster: poster,
				description: description,
				language: language,
				country: country,
				genre: genre,
				duration: duration,
				directors: country,
				writers: writers,
				producers: producers,
				key_casts: key_casts,
				about_submitter: submittersBio,
				trailer: trailer,
				movie_link: movieLink
			},
			headers: { 'Content-Type': 'multipart/form-data' }
		})
			.then((response) => {
				goto('/submit_success');
			})
			.catch((error) => {
				if (error.response) {
					console.log(error.response);
					if (error.response.data['poster']) {
						hasErrors = true;
						hasPosterError = true;
						posterError = `${error.response.data['poster']}`;
					}
					if (!error.response.data['poster']) {
						hasPosterError = false;
						posterError = '';
					}
					if (error.response.data['trailer']) {
						hasTrailerError = true;
						trailerError = `${error.response.data['trailer']}`;
					}
					if (!error.response.data['trailer']) {
						hasTrailerError = false;
						trailerError = '';
					}
					if (error.response.data['movie_link']) {
						hasErrors = true;
						hasmovie_linkError = true;
						movie_linkError = `${error.response.data['movie_link']}`;
					}
					if (!error.response.data['movie_link']) {
						hasmovie_linkError = false;
						movie_linkError = '';
					}
				}
			});
	};
</script>

<svelte:head>
	<title>BSIFF | Submit Film</title>
</svelte:head>

<section
	class="submit-film"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
>
	{#if hasErrors}
		<div class="error-container">
			<div class="error-box">
				<div class="errors">
					{#if hasPosterError}
						<h3>Image: {posterError}</h3>
					{/if}
					<br />
					{#if hasTrailerError}
						<h3>Trailer: {trailerError}</h3>
					{/if}
					<br />
					{#if hasmovie_linkError}
						<h3>Movie Link: {movie_linkError}</h3>
					{/if}
				</div>
				<p on:click={handleErrorContainer}>X</p>
			</div>
		</div>
	{/if}
	<br /><br /><br />
	<form class="form" on:submit|preventDefault={handleSubmitFile}>
		<h1 class="form__title">Submit Film</h1>

		<div class="form__group">
			<input
				type="text"
				id="title"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={title}
				required
			/>
			<label for="title" class="form__label">Title</label>
		</div>
		<!-- <label for="categories" class="form__label">Category</label> -->
		<div class="form__group">
			<select name="categories" bind:value={category} class="form__input">
				<option value="Documentary Film">Documentary Film</option>
				<option value="Feature Film">Feature Film</option>
				<option value="Short Film">Short Film</option>
				<option value="Student Film">Student Film</option>
				<option value="women in Film">Women in Film</option>
				<option value="Animated Film">Animated Film</option>
				<option value="African Film">African Film</option>
			</select>
			<label for="poster" class="form__label">Category</label>
		</div>
		<div class="form__group">
			<input
				type="file"
				id="poster"
				class="form__input"
				placeholder=""
				autocomplete="off"
				on:change={(e) => checkFile(e)}
				required
			/>
			<label for="poster" class="form__label">Poster</label>
		</div>
		<div class="form__group">
			<input
				type="text"
				id="description"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={description}
				required
			/>
			<label for="description" class="form__label">Description</label>
		</div>
		<div class="form__group">
			<input
				type="text"
				id="language"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={language}
				required
			/>
			<label for="language" class="form__label">Language</label>
		</div>
		<div class="form__group">
			<input
				type="text"
				id="genre"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={genre}
				required
			/>
			<label for="genre" class="form__label">Genres</label>
		</div>
		<div class="form__group">
			<input
				type="text"
				id="country"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={country}
				required
			/>
			<label for="country" class="form__label">Country</label>
		</div>
		<div class="form__group">
			<input
				type="text"
				id="movie_link"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={movieLink}
				required
			/>
			<label for="movie_link" class="form__label">Movie Link</label>
		</div>
		<div class="form__group">
			<input
				type="text"
				id="duration"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={duration}
				required
			/>
			<label for="duration" class="form__label">Duration</label>
		</div>
		<div class="form__group">
			<input
				type="text"
				id="writers"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={writers}
				required
			/>
			<label for="writers" class="form__label">Enter writers separated by ,</label>
		</div>
		<div class="form__group">
			<input
				type="text"
				id="directors"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={directors}
				required
			/>
			<label for="directors" class="form__label">Enter directors separated by ,</label>
		</div>
		<div class="form__group">
			<input
				type="text"
				id="producers"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={producers}
				required
			/>
			<label for="producers" class="form__label">Enter producers separated by ,</label>
		</div>
		<div class="form__group">
			<input
				type="text"
				id="key_cast"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={key_casts}
				required
			/>
			<label for="key_cast" class="form__label">Enter key casts separated by ,</label>
		</div>
		<div class="form__group">
			<textarea
				type="text"
				id="key_cast"
				class="form__input"
				placeholder=""
				autocomplete="off"
				bind:value={submittersBio}
				required
			/>
			<label for="key_cast" class="form__label">Directors Bio</label>
		</div>
		<br />
		<br />
		<div class="form__group">
			<input
				type="file"
				id="trailer"
				class="form__input"
				placeholder=""
				autocomplete="off"
				on:change={(e) => checkTrailer(e)}
				required
			/>
			<label for="trailer" class="form__label">Trailer</label>
		</div>

		<button class="form__button">Submit</button>
	</form>
</section>

<style lang="scss">
	// color variables
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
	.submit-film {
		font-family: monospace;
		font-weight: 500;

		height: auto;
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
			transition: 1s ease;

			.form__title {
				margin-bottom: 1rem;
			}

			.form__group {
				position: relative;
				height: 3rem;
				margin-bottom: 1.5rem;
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
				textarea {
					resize: none;
					width: 100%;
					height: 100px;
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
				select {
					width: 100%;
					height: 100%;
					border: 2px solid $clr-primary;
					border-radius: 0.5rem;
					background: none;
					color: inherit;
					transition: 1s ease;
					padding-left: 1.25rem;
					outline: none;
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

	// media query
	@media (max-width: 991px) {
		.submit-film {
			padding: 40px;
			.form {
				width: 45rem;
				padding: 20px;
			}
		}
	}
	@media (max-width: 768px) {
		.submit-film {
			padding: 40px;
			.form {
				width: 35rem;
				padding: 20px;
			}
		}
	}
	@media (max-width: 500px) {
		.submit-film {
			padding: 40px;
			.form {
				width: 25rem;
				padding: 20px;
			}
		}
	}
</style>
