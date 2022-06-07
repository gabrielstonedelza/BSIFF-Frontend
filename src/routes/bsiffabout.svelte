<script>
	// import cssStyles from '../styles/AboutBsiff.css';
	import { fly } from 'svelte/transition';
</script>

<svelte:head>
	<title>BSIFF | About BSIFF</title>
</svelte:head>

<section
	class="aboutbsiffcontainer"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
	id="about"
>
	<!-- heading -->
	<h2>SAVE THE DATE: SEPTEMBER 20-25TH,2022</h2>
	<p>
		The Black Star International Film Festival returns in September 2022 for its 7th edition under
		the theme, “Inspiring the Business of Film in Africa” - 4 days of celebrating international and
		African film and cinema, special events, pop-up parties, exhibitions, cultural displays,
		community screenings, artworks and photo exhibitions, BSIFF’s Industry Day and the BlackStar
		Music Concert (BMC); offering exciting, progressive, relevant and diverse opinions and
		perspectives on the history, culture, experience and business of film in Ghana and Africa.
	</p>
	<h2>Remember: BSIFF Members get the first access to tickets and discounts.</h2>
	<a href="/becomemember" class="btn">Join now or Renew</a>
</section>

<style lang="scss">
	#about {
		margin-top: 40px;
		margin-bottom: 20px;
		border-bottom: 1px solid var(--footer-border-color);
		padding: 17px 0 11px;
	}
	.aboutbsiffcontainer {
		margin: 0 auto;
		max-width: 980px;
		padding: 10 22px;
		padding-left: max(22px, env(safe-area-inset-left));
		padding-right: max(22px, env(safe-area-inset-right));
		h2 {
			padding: 20px;
			font-size: 28px;
			line-height: 1.08349;
			font-weight: 600;
			letter-spacing: -0.003em;
			font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
				sans-serif;
		}
		p {
			padding: 20px;
			font-size: 21px;
			line-height: 1.381;
			font-weight: 400;
			letter-spacing: 0.011em;
			font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
				sans-serif;
			color: #86868b;
		}
		.btn {
			// display: flex;
			// justify-content: center;
			padding-left: 20px;
			padding-right: 20px;
			padding-top: 10px;
			padding-bottom: 10px;
			background-color: #c8a461;
			color: #000;
			border-radius: 24px;
			text-align: center;
		}
	}
</style>
