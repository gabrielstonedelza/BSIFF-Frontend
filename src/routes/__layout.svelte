
<script>
	import Logo from '../assets/images/logo-1.png';
	import cssStyles from '../styles/header/header.css';
	import aboutStyles from '../styles/AboutBsiff.css';
	let active = false;
	function closeMenu(){

	}
</script>

<header>
	<a href="/" class="logo">
		<div class="logoandtitle">
			<img src={Logo} alt="" />
			<span>|</span>
			<h2>BSIFF</h2>
		</div>
	</a>
	<input type="checkbox" id="menu-bar" />
	<label for="menu-bar">Menu</label>
	<nav class="navbar">
		<ul>
			<li>
				<a href="#">BSIFF 2022 </a>
				<ul>
					<li><a href="/bsiffabout">About</a></li>
					<li><a href="/bsiffsubmissions">Submissions</a></li>
					<li><a href="/bsiffofficialselection">Official Selection</a></li>
				</ul>
			</li>
			<li>
				<a href="#">About </a>
				<ul>
					<li>
						<a href="#">About BSIFF</a>
						<ul>
							<li><a href="/whoweare">Who We Are</a></li>
							<li><a href="/advisoryboard">Advisory Board</a></li>
							<li><a href="/squad">The Squad</a></li>
							<li><a href="">Contact</a></li>
						</ul>
					</li>
					<li>
						<a href="#">Our Programming</a>
						<ul>
							<li>
								<a href="/bsiffeduproject">Off-Peak Programs </a>
							</li>
							<li>
								<a href="/bsiffpeakprograms">Peak Programs +</a>
								<ul>
									<li>
										<a href="/filmfestival">Film Festival</a>
									</li>
									<li>
										<a href="/blackmusicconcert">The Blackstar Music Concert </a>
									</li>
									<li>
										<a href="/awards">The BlackStar Awards & Closing Night </a>
									</li>
									<li>
										<a href="/support">SUPPORT BSIFF </a>
									</li>
								</ul>
							</li>
						</ul>
					</li>
				</ul>
			</li>
			<li><a href="/becomemember">Become a Member</a></li>

			<li><a href="/donate">Donate</a></li>
			<li><a href="/register">Register</a></li>
		</ul>
	</nav>
</header>
<br />
<br />
<br />
<!-- <br />
<br /> -->
<slot />
