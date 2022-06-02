<script>
	// import cssStyles from '../styles/AboutBsiff.css';
	import { fly } from 'svelte/transition';
</script>

<svelte:head>
	<title>BSIFF | About BSIFF</title>
</svelte:head>

<section class="aboutbsiffcontainer" in:fly={{ y: 50, duration: 500,delay: 500 }} out:fly={{ duration: 500 }}>
	<!-- heading -->
	<h2>SAVE THE DATE: SEPTEMBER 20-24TH,2022</h2>
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
