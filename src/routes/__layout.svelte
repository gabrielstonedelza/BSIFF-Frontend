
<script>
	import Logo from '../assets/images/logo-1.png';
	import cssStyles from '../styles/header/header.css';
	import aboutStyles from '../styles/AboutBsiff.css';
	let active = false;
	let menu_opened = false;
	function toggleMenu(){
		menu_opened = !menu_opened;
		console.log("toggleMenu")
	}
	function handleMenuOpened(){
		menu_opened = true;
	}
	function handleMenuClosed(){
		menu_opened = false;
	}
</script>

<header>
	<a href="/" class="logo">
		<div class="header1">
			<h6>BSIFF 2022: September 20 - 25 | Accra, Ghana</h6>
		</div>
		<div class="logoandtitle">
			<img src={Logo} alt="" />
			<span>|</span>
			<h2>BSIFF</h2>
		</div>
	</a>
	<input type="checkbox" id="menu-bar" on:click={toggleMenu}/>
	<label for="menu-bar">Menu</label>
	
	<nav class="navbar">
		<ul>
			<li>
				<p>BSIFF 2022 </p>
				<ul>
					<li><a href="/bsiffabout">About</a></li>
					<li><a href="/bsiffsubmissions" on:click={() =>(active = false)}>Submissions</a></li>
					<li><a href="/bsiffofficialselection">Official Selection</a></li>
				</ul>
			</li>
			<li>
				<p>About </p>
				<ul>
					<li>
						<p href="">About BSIFF</p>
						<ul>
							<li><a href="/whoweare">Who We Are</a></li>
							<li><a href="/advisoryboard">Advisory Board</a></li>
							<li><a href="/squad">The Squad</a></li>
							<li><a href="/gallery">Gallery</a></li>
						</ul>
					</li>
					<li>
						<p>Our Programming</p>
						<ul>
							<li>
								<a href="/bsiffeduproject">Off-Peak Programs </a>
							</li>
							<li>
								<a href="/bsiffpeakprograms" on>Peak Programs +</a>
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
			<li><a href="/becomemember">Join</a></li>

			<li><a href="/donate">Donate</a></li>
			<li><a href="/login">Login</a></li>
		</ul>
	</nav>

	
</header>
<br />
<br />
<br />
<!-- <br />
<br /> -->
<slot />
