<script>
	// import cssStyles from '../styles/AboutBsiff.css';
	import { fly } from 'svelte/transition';
</script>

<svelte:head>
	<title>BSIFF | Submission</title>
</svelte:head>

<section
	class="submissions"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
	id="sub-container"
>
	<p>
		Film submissions into the 7th annual Black Star International Film Festival, running from
		September 20 to 24, 2022, are now closed. Thank you to everyone who submitted their film.
		Submissions for our 8th edition will open in January 2023.
	</p>
	<h4>CATEGORIES</h4>
	<p>
		BSIFF accepts submissions from Africa and all over the world annually, from January till March,
		via Filmfreeway
	</p>
	<h3>Submission categories include:</h3>
	<ul class="subcat-list">
		<li>
			<p>
				- Documentary Film: A non-fiction film about real events and people, often avoiding
				traditional narrative structures. Documentary [is] the creative treatment of actuality
			</p>
		</li>
		<li>
			<p>- Feature Film: Should be 60 mins or more long.</p>
		</li>
		<li>
			<p>
				- Short Film: The film should be less than 60 min. It's considered short once it's less than
				60 mins
			</p>
		</li>
		<li>
			<p>
				- Student Film (The Inspire Award): This category is set to award student filmmakers thus,
				the film must be made entirely by students and without financial or technical support from
				broadcasters. Evidence of a student card and an email confirmation from the Head of the
				department is a must.
			</p>
		</li>
		<li>
			<p>
				- Women in Film: Film must have a predominantly female crew. Any three of the Producer,
				directors, cinematographers, and/or Writers must be women.
			</p>
		</li>
		<li>
			<p>- Animated Film: An animated film from any part of the world.</p>
		</li>
		<li>
			<p>
				- African Films (The Black Star Award): Film that connects to the special story of Africa
				and stories that highlight special issues peculiar to the continent of Africa. Films must
				have a predominantly African crew. Any three of the Producer, directors, cinematographers,
				and/or Writers must be Africans.
			</p>
		</li>
		<li>
			<p>
				- Music Video: To award music videos worldwide that have strong story-telling,
				conceptualization, and film production. We accept music video submissions from all over the
				world. Music Videos must be under 10 minutes and from any year regardless of budget,
				popularity, or language.
			</p>
		</li>
	</ul>
	<h4>Rules And Eligibility</h4>
	<ul>
		<li>
			<h3>SUBMISSION FEES</h3>
			<br />
			<p>
				This year, BSIFF is giving priority to student films and African stories hence, submission
				to the Student category is free whilst the African film category is $5. Submission fees for
				all other categories are $20. Gold Members on FilmFreeway get further discounts.
			</p>
		</li>
		<li>
			<h3>SUBTITLES</h3>
			<br />
			<p>
				Non-English language works must have English subtitles at the time submitted. Dialogue lists
				will not be accepted.
			</p>
		</li>
		<li>
			<h3>PRODUCTION YEAR</h3>
			<br />
			<p>
				All films submitted must have been completed after January 1, 2021. Priority will be given
				to films made in 2022 & 2023.<br />
				Submissions may be work-in-progress form; however, films that are not final cuts must be clearly
				marked Work in Progress (“WIP”) or Rough Cut' with an indication of what will change or what
				is missing (e.g., temp sound, Avid output, missing animation, etc.) either indicated in the film
				cut itself or within the copy display in the streaming link. As long as the streaming link remains
				the same and password does not change you may update the link with newer cuts as they are available
				up until the last applicable entry deadline noted above.
			</p>
		</li>
		<li>
			<h3>MULTIPLE ENTRIES</h3>
			<br />
			<p>
				Each film must be individually submitted and accompanied by its own completed online entry
				form; please do not send links to multiple film entries in your online entry form, as any or
				all of them may be disqualified.
			</p>
		</li>
		<li>
			<h3>AWARDS</h3>
			<br />
			<p>
				Unless otherwise agreed by the Festival in writing, awards will be given to the winning film
				Director (as identified in the Film Information Form) on behalf of the film. Award
				eligibility is subject to any restrictions or conditions imposed by applicable laws and
				regulations (international, federal, state, or otherwise), and the award recipient is
				responsible for all applicable taxes, customs, tariffs, insurance, and similar charges or
				costs (if any).
			</p>
		</li>
	</ul>
	<br />
	<a href="/submit_film" class="btn">SUBMIT NOW</a>
</section>

<style lang="scss">
	#sub-container {
		margin-top: 40px;
		margin-bottom: 20px;
		border-bottom: 1px solid var(--footer-border-color);
		padding: 17px 0 11px;
	}
	.submissions {
		margin: 0 auto;
		max-width: 980px;
		padding: 0 22px;
		padding-left: max(22px, env(safe-area-inset-left));
		padding-right: max(22px, env(safe-area-inset-right));

		ul {
			list-style-type: none;
			margin: 0;
			padding: 0 17px;
			li {
				font-size: 12px;
				line-height: 1.33337;
				font-weight: 400;
				letter-spacing: -0.01em;
				font-family: 'SF Pro Text', 'Myriad Set Pro', 'SF Pro Icons', 'Apple Legacy Chevron',
					'Helvetica Neue', 'Helvetica', 'Arial', sans-serif;
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
		h4 {
			padding: 20px;
			font-size: 28px;
			line-height: 1.08349;
			font-weight: 600;
			letter-spacing: -0.003em;
			font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
				sans-serif;
		}
		h3 {
			padding: 20px;
			font-size: 20px;
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
			margin-left: 40px;
		}
	}

	@media (max-width: 768px) {
		.submissions {
	
			margin: 0 auto;
			max-width: 980px;
			padding: 0 22px;
			padding-left: max(22px, env(safe-area-inset-left));
			padding-right: max(22px, env(safe-area-inset-right));
		}
	}
</style>
