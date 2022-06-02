<script>
	// import cssStyles from '../styles/AboutBsiff.css';
	import { fly } from 'svelte/transition';
</script>
<svelte:head>
	<title>BSIFF | BSIFF EDU</title>
</svelte:head>

<section class="eduproject" id="edu-project" in:fly={{ y: 50, duration: 500, delay: 500 }}
out:fly={{ duration: 500 }}>
	<h2>BSIFF EDU Projects</h2>
	<p>
		BSIFF EDU is committed to inspiring a generation of African filmmakers. Our aim is to provide
		global standard film education, and skill training to independent, emerging young and aspiring
		film and music artists in Ghana and Africa.
	</p>
	<p>Annual projects undertaken by BSIFF EDU includes:</p>
	<h2>Inspire</h2>
	<p>
		Inspire is a 2-day workshop and development programme targeted at nurturing film talents in
		Ghana with the aim of supporting students and young people within the ages 18-25 interested in
		filmmaking with film education, raising film professionals and giving students practical
		education and experience with cinema and the film industry, serving as a bridge between academia
		and the real world.
	</p>
	<p>Participants must be registered members of BSIFF (“BSIFF Stars”).</p>
	<p>
		Each year, BSIFF Edu collaborates with professional filmmakers and film institutions from around
		the world to teach (virtually or physically) emerging and aspiring filmmakers through an
		intensive two-day workshop and masterclass.
	</p>
	<h2>Film-Music Conference</h2>
	<p>
		Film-Music is a whole film and music business genre that is rarely studied or talked about on
		the African Continent.
	</p>
	<p>
		The maiden edition of the film-music conference will run in August under the topic: “Exploring
		the Art and Business of Writing & Composing Music for Film, Television and Video Games.”
	</p>
	<p>
		This event is targeted at filmmakers including established and aspiring film directors,
		screenwriters, and producers, music composers, sound designers, music producers, songwriters,
		music lovers, singers and artistes. It focuses on important topics related to film-music such as
		preparing and recording a score, the film-music business (how to succeed, contracts and fees,
		publishing, royalties, copyrights) and much more. The conference is aimed at connecting
		filmmakers to musicians, sound designers, song writers, music lovers, singers & artistes.
	</p>
	<h2>BOOK A SEAT NOW!</h2>
	<h3>Screenwriting Project (Could name this after your brand)</h3>
	<p>
		The BSIFF Edu community screenwriting mentorship program and competition, is targeted at
		screenwriters in Ghana and Africa, with the aim of developing authentic story-tellers who embody
		the culture, history and experience of their countries.
	</p>
	<p>
		Interested screenwriters will present to BSIFF, a script for a short film that is likely to last
		within 1-10 mins long.
	</p>
	<p>
		Participants will undergo a short but intensive virtual/physical workshop with mentors and then
		they would be required to submit a script under a theme.
	</p>
	<p>
		The best script will win a cash prize during the film festival in September. With the support of
		partners, we will help the winner develop their story into a short film. The short film will be
		shown at the Black Star International Film Festival as a Special PAtv-BSIFF segment and on other
		relevant channels.
	</p>
</section>

<style lang="scss">
	#edu-project {
		margin-top: 40px;
		margin-bottom: 20px;
		border-bottom: 1px solid var(--footer-border-color);
		padding: 17px 0 11px;
	}
	.eduproject {
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
				padding: 20px;
		}
		h2 {
			padding: 20px;
			line-height: 1.08349;
			font-weight: 600;
			letter-spacing: -0.003em;
			font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
				sans-serif;
		}
	}
</style>
