<script>
	// import cssStyles from '../styles/AboutBsiff.css';
	import { fly } from 'svelte/transition';
</script>
<svelte:head>
	<title>BSIFF | Blackstar Music Concert</title>
</svelte:head>

<section class="concert" id="black-concert" in:fly={{ y: 50, duration: 500, delay: 500 }}
out:fly={{ duration: 500 }}>
	<h2>Blackstar Music Concert</h2>
	<p>
		The BlackStar Music Concert was introduced into the festival in 2018. The idea of a music
		concert within the film festival was born because we recognize that music is one of the most
		important elements in film, and it is highly regarded for manipulating emotions and immersing
		viewers into a story. The power of music in film cannot be underemphasized because more often
		without music, there is no excitement and nothing memorable.
	</p>
	<p>
		With the Concert, our aim is to give emerging artistes within the Ghanaian & African music space
		a platform for their talents to be recognized, appreciated and help them secure support from
		investors or people, who want to help manage their careers, help them place jobs and develop
		great musical/sound projects that could possibly be used in films.
	</p>
	<p>
		The diversity of the BlackStar Concert is its unique element and as such affords all kinds of
		musicians or performers, right down from singer/songwriters, rappers, instrumentalists etc. who
		can create their own music. With BSIFF’s partnership with key stakeholders in the film and music
		industry, some of these artists gain great value that can push their careers to the next level.
	</p>
	<p>
		Ghanaian talents that graced our stages in the early stages of their careers include Cina Soul,
		Darko Vibes, Asi Renie, Ria Boss, Essilfie, Beryl, Dedeba, Sefa, ToluDadi
	</p>
	<br />
	<a href="https://www.youtube.com/channel/UCyTMomHPU4760bOoq2ycgkg" class="btn" target="_blank">WATCH CONCERT VIDEOS HERE </a>
</section>

<style lang="scss">
	#black-concert {
		margin-top: 40px;
		margin-bottom: 20px;
		border-bottom: 1px solid var(--footer-border-color);
		padding: 17px 0 11px;
	}
	.concert {
		margin: 0 auto;
		max-width: 980px;
		padding: 0 22px;
		padding-left: max(22px, env(safe-area-inset-left));
		padding-right: max(22px, env(safe-area-inset-right));
		p {
			font-size: 21px;
			line-height: 1.381;
			font-weight: 400;
			letter-spacing: 0.011em;
			font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
				sans-serif;
			color: #86868b;
		}
		h2 {
			padding-top: 20px;
			padding-bottom: 20px;
			font-size: 28px;
			line-height: 1.08349;
			font-weight: 600;
			letter-spacing: -0.003em;
			font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
				sans-serif;
		}
		.btn {
			padding-left: 20px;
			padding-right: 20px;
			padding-top: 10px;
			padding-bottom: 10px;
			background-color: #c8a461;
			color: #000;
			border-radius: 24px;
		}
	}
</style>
