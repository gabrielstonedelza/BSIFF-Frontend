<script>
	// import cssStyles from '../styles/AboutBsiff.css';
	import { fly } from 'svelte/transition';
</script>
<svelte:head>
	<title>BSIFF | Film Festival</title>
</svelte:head>

<section class="ffestival" id="festival" in:fly={{ y: 50, duration: 500, delay: 500 }}
out:fly={{ duration: 500 }}>
	<h2>Film Festival</h2>
	<p>
		The Black Star International Film Festival is our year-round activity climax. It is a 5-day film
		festival dedicated to discover, display and celebrate the works of independent film and music
		artists in Africa especially, to audiences (existing and new) around the World.
	</p>
	<p>
		BSIFF Official Selection films are showcased within a powerful programming. The film festival
		attracts film tourists, filmmakers (professional and emerging), students’ and other film, cinema
		and music lovers.
	</p>
	<h3>BSIFF Industry Day</h3>
	<p>
		BSIFF’s Industry Day happens annually within the Festival. The aim of Industry day is to bring
		together all relevant stakeholders in the film and cinema sector, under a common umbrella to
		discuss relevant sector issues via varying panel sessions, keynote speeches and masterclasses.
	</p>
	<p>Industry Day seeks to:</p>
	<ul>
		<li>
			<p>- to engage and sensitize industry to developments and interventions</p>
		</li>
		<li>
			<p>- to propose steps to address the identified gaps within the industry</p>
		</li>
		<li>
			<p>
				- to identify the role that government can play in the area of policy interventions and
				actions
			</p>
		</li>
		<li>
			<p>- to map out the immediate expected outcomes for both the sector and the economy.</p>
		</li>
	</ul>
</section>

<style lang="scss">
	#festival {
		margin-top: 40px;
		margin-bottom: 20px;
		border-bottom: 1px solid var(--footer-border-color);
		padding: 17px 0 11px;
	}
	.ffestival {
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
	}
</style>
