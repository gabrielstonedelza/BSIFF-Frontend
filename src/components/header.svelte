<script>
    import Logo from '../assets/images/logo-1.png';
    import cssStyles from '../styles/header/header.css';

</script>

<nav class="mynav">
    <header class="nav-container">
        <!-- logo and name -->
        <div class="logo-name">
            <div class="logo">
                <img src={Logo} alt="">
            </div>
            <span>|</span>
            <div class="title">
                <h3>BSIFF</h3>
            </div>
        </div>
        <ul>
            <li>
                <a href="/">Home</a>
            </li>
            <li>
                <a href="/bsiff">BSIFF 2022</a>
            </li>
            <li>
                <a href="/becomemember">Become a Member</a>
            </li>
            <li>
                <a href="/donate">Donate</a>
            </li>
            <li>
                <a href="/about">About</a>
            </li>
        </ul>
    </header>
</nav>