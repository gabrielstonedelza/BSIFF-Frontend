<script>
    import Facebook from "../assets/images/icons/facebook.png"
    import Instagram from "../assets/images/icons/instagram.png"
    import Twitter from "../assets/images/icons/twitter.png"
    import Youtube from "../assets/images/icons/youtube.png"
</script>

<div class="social-media">
    <div class="links">

        <a href="https://web.facebook.com/BSIFF.org" target="_blank">
            <img src={Facebook} alt="facebook logo">
        </a>
        <a href="https://www.youtube.com/watch?v=IGSLw-seetE" target="_blank">
            <img src={Instagram} alt="instagram logo">
        </a>
        <a href="https://twitter.com/theBSIFF?s=08" target="_blank">
            <img src={Twitter} alt="twitter logo">
        </a>
        <a href="https://www.youtube.com/watch?v=IGSLw-seetE" target="_blank">
            <img src={Youtube} alt="youtube logo">
        </a>
    </div>
</div>

<style lang="scss">
    .social-media{
        position: fixed;
        margin-top:250px;
        padding: 10px;
        z-index: 1000;
        background:rgba(0,0,0,.8);
        border-top-right-radius: 20px;
        border-bottom-right-radius: 20px;
        .links{
            float: right;
            display: flex;
            flex-direction: column;
        
            gap: 1rem;
            a{
            img{
                width: 30px;
                height: 30px;
            }
        }
        }
    }
    // media query
    @media(max-width:991px){
        .social-media{
            margin-top: 300px;
        }
    }
    @media(max-width:768px){
        .social-media{
            margin-top: 300px;
        }
    }
</style>