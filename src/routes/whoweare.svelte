<script>
	// import cssStyles from '../styles/AboutBsiff.css';
	import { fly } from 'svelte/transition';
</script>

<svelte:head>
	<title>BSIFF | Who we are</title>
</svelte:head>

<section class="whoweare" id="whowearecontainer" in:fly={{ y: 50, duration: 500, delay: 500 }}
out:fly={{ duration: 500 }}>
	<h3>
		THE BLACK STAR INTERNATIONAL FILM FESTIVAL (BSIFF) IS A MOVEMENT OF CHANGE MAKERS INSPIRING THE
		BUSINESS OF FILM
	</h3>
	<p>
		Like the Black Star, BSIFF provides a platform that inspires hope & love for film, cinema, and
		film-music, supporting independent African filmmakers to reach the right network, worldwide
		audience, film education, acquire relevant skills and distribution opportunities that push their
		creative boundaries beyond limit.
	</p>
	<p>
		BSIFF aspires to bridge the gap between Africa Cinema and the world. To achieve this, we are
		committed to:
	</p>
	<ul>
		<li>
			<p>
				- discovering, displaying, and celebrating the works of independent film artists in Ghana
				and Africa to audiences (existing and new) around the World, through our film festival.
			</p>
		</li>
		<li>
			<p>
				- educating, nurturing, and providing skill training & film distribution opportunities to
				independent emerging and aspiring film artists in Ghana and Africa, through our educational
				platform, BSIFF Edu.
			</p>
		</li>
		<li>
			<p>
				- building a community of film enthusiasts and providing a platform where they can connect,
				network, foster the exchange of cultures and explore business opportunities and investments.
			</p>
		</li>
	</ul>
</section>

<style lang="scss">
	#whowearecontainer {
		margin-top: 40px;
		margin-bottom: 20px;
		border-bottom: 1px solid var(--footer-border-color);
		padding: 17px 0 11px;
	}
	.whoweare {
		margin: 0 auto;
		max-width: 980px;
		padding: 0 22px;
		padding-left: max(22px, env(safe-area-inset-left));
		padding-right: max(22px, env(safe-area-inset-right));

        h3 {
			padding-top: 20px;
			padding-bottom: 20px;
			font-size: 28px;
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
		}
	}
</style>
