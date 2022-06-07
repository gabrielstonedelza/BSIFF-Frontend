<script>
	import { fly } from 'svelte/transition';

	import Apiorkor from '../assets/images/Apiorkor.png';
	import KBoachie from '../assets/images/KofiBoachie.png';
	import Helga from '../assets/images/Helga.png';
	import Nico from '../assets/images/NicoAProfile.png';
	import Farai from '../assets/images/farai.jpeg';
</script>

<svelte:head>
	<title>BSIFF | Advisoryboard</title>
</svelte:head>

<section
	class="adviceboard"
	id="adviceboard-container"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
>
	<br />
	<br />
	<div class="helga">
		<div class="about">
			<div class="about-poster">
				<img src={Helga} alt="" />
				<h2>HELGA-LIZ HABERFELLNER (WRITER, PRODUCER, DIRECTOR - TEACHER)</h2>
			</div>
			<p>
				Helga has spent more than 30years in the Canadian film and TV industry as both a filmmaker
				and a professor. Her filmmaking experience stretches from researching to writing and
				budgeting, to directing, producing and editing. She won many awards for her work and was
				recognized as a film doctor.
			</p>
			<p>
				Her greatest passion however, was making long format science and social science
				documentaries. Her independently produced films have been shown on Discovery Canada, The
				Life Network, Canal Plus, the CBC, Radio Canada, and CTV, and have appeared in the USA,
				England, Turkey, Australia, Germany, France and Japan. One of her documentaries was selected
				by Discovery Canada to kick off the Canadian Discovery Channel at Hot Docs in 1996.
			</p>
			<p>
				She also has extensive teaching experience at both the community college and university
				levels and taught courses in visual language, film aesthetics, filmmaking, documentary
				production, editing, cinematography, storytelling, media writing, editing concepts,
				production budgeting, and information and communication theory. She and her husband combined
				their filmmaking knowledge and experiences to create workshops for burgeoning filmmakers in
				Ghana and Namibia which is how she first got involved with BSIFF.
			</p>
		</div>
	</div>
	<div class="apiorkor">
		<div class="about">
			<div class="about-poster">
				<img src={Apiorkor} alt="" />
				<h2>APIORKOR SEYRAM ASHONG-ABBEY</h2>
			</div>
			<p>
				Apiorkor is a Ghanaian-American Poet, Writer/Author, Literary Scholar and Critic, Media
				Practitioner, TED Speaker, Activist and Versatile Creative of Ga-Daŋme and Ewe ancestry. Her
				work is noted for its rare narrative, prosaic, journalistic nature, which is uncommon in
				Poetry. The sharp, vivid imagery of my pieces has been featured in many journals and
				academic theses.
			</p>
			<p>
				She reads her Poetry on stage and often infuses it with varied music forms, Contemporary
				Dance and alternative Art. Over the past three and a half years, she has led a campaign to
				have Ghanaian (and African) Poets, Poetry, and Artists properly documented in local media
				sources and on Wikipedia. This has led to the gains that the Wikimedia User Group in Ghana
				is currently making, in this regard.
			</p>
			<p>
				Additionally, Apiorkor is a member of the Poetry Association of Ghana's Executive Board and
				a Director-At-Large of the Democrats Abroad Africa Committee's ExCom, as the Coordinator of
				Democrats Abroad - Ghana. She is the Head of Programmes Production at Accra-based Citi 97.3
				FM and Citi TV, where she is also a Broadcaster and Producer. She teaches, mentors and
				counsels Poets, Writers, Creatives and young people (especially young women).
			</p>
		</div>
	</div>

	<div class="kofi-boachie">
		<div class="about">
			<div class="about-poster">
				<img src={KBoachie} alt="" />
				<h2>KOFI BOACHIE- ANSAH</h2>
			</div>
			<p>
				Kofi is a multi-disciplinary artist and creative entrepreneur who has been actively involved
				in private business ventures in the creative sector and is an advocate for the re-thinking,
				realization and creation of sustainable structures and frameworks for the arts in Ghana and
				Africa.
			</p>
			<p>
				His creative work is expansive with a practice at an intersection of film, still and
				motion-graphics, 2D and 3D animation, visual effects, record production, ethnomusicology,
				sound design, foley, ADR, writing and arranging across multiple genres, tracking, mixing,
				FoH, Cue and Monitor for sound reinforcement/ live sound, film scores, acoustic design
				solutions, studio design, advertising campaigns and brand audits, print and digital design,
				painting and sculpture and cymatics.
			</p>

			<p>
				Kofi has worked on several independent film productions and television series, and with
				multiple artists locally and internationally across multiple genres.
			</p>
		</div>
	</div>
	<div class="nico">
		<div class="about">
			<div class="about-poster">
				<img src={Nico} alt="" />
				<h2>NICO ABOTE</h2>
			</div>
			<p>
				Nico Abote is a passionate Broadcast Media-Communications Specialist with over 14 years’
				experience within the film and television industry. He received special training in
				broadcast media, TV broadcasting from Journalism Institute of South Africa and is currently
				studying Film & Video Production at Toronto Film School. His professional interests focus on
				television/film production as a director, producer and editor.
			</p>
			<p>
				Currently working as the Digital Broadcast Production Manager & Producer at Western Standard
				New Media Inc. He is also leading the following projects: The Dance Matchmaker TV Series as
				Director, The War-Hammer Documentary Series as Director, Play Afrika TV Platform + Content
				development, as the Executive Producer and Co-Founder, and other media related consultancy
				work in Canada & across Africa.
			</p>
			<p>
				He is also a member of Calgary Society of Independent Filmmakers (CSIF), holds a permit with
				IATSE Local 212. Nico is also the Lead Production Executive with the Canada University
				Shooting Federation (CUSF) and also serves with The Gold-Mind Project as media producer
				among other organizations in Canada & Africa. In addition, he serves as board member for
				Chengeto Africa, a Southern African based non-profit, that utilizes Media as a form to
				advocate for women & girl child rights.
			</p>
		</div>
	</div>
	<div class="farai">
		<div class="about">
			<div class="about-poster">
				<img src={Farai} alt="" />
				<h2>Farai Elton MJANANA</h2>
			</div>
			<p>
				Writer and Director Farai has over 15 years experience in the industry with written work that has gone into production and publishing in Zimbabwe. On top of writing for Film with credits including the documentary film ‘Absolute Jiti: The Bhundu Boys’ Story (2007) and TV ‘The Team’ (2012), Farai written extensively for Radio and Theatre as well. His directing credits are mostly for theatre including working as Theatre Consultant for the Harare International Festival of the Arts (HIFA) for over ten years. Farai also served as Festival Director for the Zimbabwe International Film Festival for four years between 2013 -2016 editions. Farai currently lives and works in London, United Kingdom, where he has just completed a Certificate for the TV Series Bible Creation Course with the National Film and Television School. 
			</p>
		</div>
	</div>
</section>

<style lang="scss">
	#adviceboard-container {
		margin-top: 40px;
		margin-bottom: 20px;
		border-bottom: 1px solid var(--footer-border-color);
		padding: 17px 0 11px;
	}
	.adviceboard {
		margin: 0 auto;
		max-width: 1200px;
		padding-top: 22px;
		padding-left: max(22px, env(safe-area-inset-left));
		padding-right: max(22px, env(safe-area-inset-right));
		.helga,
		.apiorkor,
		.kofi-boachie,
		.nico,.farai {
			display: flex;
			gap: 1rem;
			flex-direction: column;
			// flex-wrap: wrap;
			.about-poster {
				display: flex;
				align-items: center;
				padding-left: 10px;
				img {
					width: 200px;
					height: 200px;
					border-radius: 50%;
					border: solid 3px #c8a461;
				}
			}
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
		h2 {
			padding: 20px;
			font-size: 28px;
			line-height: 1.08349;
			font-weight: 600;
			letter-spacing: -0.003em;
			font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
				sans-serif;
		}
	}
	@media (max-width: 768px) {
		.adviceboard {
			p {
				padding: 20px;
				font-size: 15px;
				line-height: 1.381;
				font-weight: 400;
				letter-spacing: 0.011em;
				font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
					sans-serif;
				color: #86868b;
			}
			h2 {
				padding: 20px;
				font-size: 18px;
				line-height: 1.08349;
				font-weight: 600;
				letter-spacing: -0.003em;
				font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
					sans-serif;
			}
			.helga,
			.apiorkor,
			.kofi-boachie,
			.nico {
				display: flex;
				gap: 1rem;
				flex-direction: column;
				// flex-wrap: wrap;
				.about-poster {
					img {
						width: 150px;
						height: 150px;
						border-radius: 50%;
						border: solid 3px #c8a461;
					}
				}
			}
		}
	}

	@media (max-width: 500px) {
		.adviceboard {
			p {
				padding: 20px;
				font-size: 15px;
				line-height: 1.381;
				font-weight: 400;
				letter-spacing: 0.011em;
				font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
					sans-serif;
				color: #86868b;
			}
			h2 {
				padding: 20px;
				font-size: 18px;
				line-height: 1.08349;
				font-weight: 600;
				letter-spacing: -0.003em;
				font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
					sans-serif;
			}
			.helga,
			.apiorkor,
			.kofi-boachie,
			.nico {
				display: flex;
				gap: 1rem;
				flex-direction: column;
				// flex-wrap: wrap;
				.about-poster {
					display: flex;
					flex-direction: column;
					img {
						width: 100px;
						height: 100px;
						border-radius: 50%;
						border: solid 3px #c8a461;
					}
				}
			}
		}
	}
</style>
