<script>
	// import cssStyles from '../styles/AboutBsiff.css';
	import { fly } from 'svelte/transition';
</script>
<svelte:head>
	<title>BSIFF | Awards</title>
</svelte:head>

<section class="awards" id="awards-night" in:fly={{ y: 50, duration: 500, delay: 500 }}
out:fly={{ duration: 500 }}>
	<h2>The BlackStar Awards & Closing Night</h2>
	<p>
		Annually during the Closing & Awards Night of the Festival, the works of deserving independent
		filmmakers are recognized and rewarded.
	</p>
	<ul>
		<li>
			<p>- Yaa Asantewaa Best Feature Film award</p>
		</li>
		<li>
			<p>- Yaa Asantewaa Best Documentary Film award</p>
		</li>
		<li>
			<p>- Yaa Asantewaa Best Animated Film award</p>
		</li>
		<li>
			<p>- Yaa Asantewaa Best Short Film award</p>
		</li>
		<li>
			<p>- Yaa Asantewaa Best Woman in Film award</p>
		</li>
		<li>
			<p>- Yaa Asantewaa Best Music Video award</p>
		</li>
		<li>
			<p>- The Black Star Award for Best African Film d</p>
		</li>
		<li>
			<p>- Yaa Asantewaa Inspire Award</p>
		</li>
		<li>
			<p>- Best Screenwriter Award</p>
		</li>
		<li>
			<p>
				- The Golden Star Award of Excellence (Awarded to prominent film figures for their
				contribution to film in Africa)
			</p>
		</li>
	</ul>
	<p>
		In 2020, BSIFF offered the Yaa Asantewaa-GOETHE award valued at $1500 to winners of the Best
		Ghanaian Film award . In 2017, BSIFF offered the Yaa Asantewaa-UNDP awards valued at $3000 each
		to 6 winning filmmakers.
	</p>
	<h3>CHECK OUT THE AWARD WINNERS FOR BSIFF 2021</h3>
</section>

<style lang="scss">
	#awards-night {
		margin-top: 40px;
		margin-bottom: 20px;
		border-bottom: 1px solid var(--footer-border-color);
		padding: 17px 0 11px;
	}

	.awards {
		margin: 0 auto;
		max-width: 980px;
		padding: 0 22px;
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
		h3 {
			padding-top: 20px;
			padding-bottom: 20px;
			font-size: 20px;
			line-height: 1.08349;
			font-weight: 600;
			letter-spacing: -0.003em;
			font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
				sans-serif;
		}
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
			font-size: 21px;
			line-height: 1.381;
			font-weight: 400;
			letter-spacing: 0.011em;
			font-family: 'SF Pro Display', 'SF Pro Icons', 'Helvetica Neue', 'Helvetica', 'Arial',
				sans-serif;
			color: #86868b;
			padding: 20px;
		}
	}
</style>
