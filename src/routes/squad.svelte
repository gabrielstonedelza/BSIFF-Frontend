<script>
	// import cssStyles from '../styles/AboutBsiff.css';
	import { fly } from 'svelte/transition';
</script>
<svelte:head>
	<title>BSIFF | The Squad</title>
</svelte:head>

<section class="squad"  id="squad-container" in:fly={{ y: 50, duration: 500, delay: 500 }}
out:fly={{ duration: 500 }}>
	<h2>The Squad</h2>
	<ul>
		<li>
			<p>JULIET YAA ASANTEWA ASANTE - FOUNDING PRESIDENT</p>
		</li>
		<li>
			<p>PHILIPPA AMA BENTUMA ARTHUR - DIRECTOR/FESTIVAL PRODUCER</p>
		</li>
		<li>
			<p>TOSIN OJELABI - EVENTS MANAGER/SUPERVISOR</p>
		</li>
		<li>
			<p>CASTRO - TECHNICAL LEAD</p>
		</li>
		<li>
			<p>BEN ADJEI - PROJECT LEAD, BSIFF EDU</p>
		</li>
		<li>
			<p>NAA DEDE TETTEH - PROJECT LEAD, BLACKSTAR MUSIC CONCERT (BMC)</p>
		</li>
		<li>
			<p>FLORENCE BOATENG - CONTENT WRITER</p>
		</li>
		<li>
			<p>KELVIN SITTIE - SOCIAL MEDIA MANAGER</p>
		</li>
		<li>
			<p>DAVID NSENKYIRE - ASSISTANT</p>
		</li>
	</ul>
</section>


<style lang="scss">
	#squad-container {
		margin-top: 40px;
		margin-bottom: 20px;
		border-bottom: 1px solid var(--footer-border-color);
		padding: 17px 0 11px;
	}
	.squad{
		margin: 0 auto;
		max-width: 980px;
		padding: 0 22px;
		padding-left: max(22px, env(safe-area-inset-left));
		padding-right: max(22px, env(safe-area-inset-right));
		h2{
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
			padding: 10 17px;
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
	}

</style>