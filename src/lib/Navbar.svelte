<script lang="ts">
    import SmoothA from "./SmoothA.svelte";
    import MainNavButton from "./MainNavButton.svelte";

    let colorScheme: string = window.matchMedia('(prefers-color-scheme: dark)').matches ? '-dark' : '';

    window.matchMedia("(prefers-color-scheme: dark)").addEventListener("change", () => {
        colorScheme = window.matchMedia('(prefers-color-scheme: dark)').matches ? '-dark' : '';
    });
</script>

<!--<div goto_id="navbar-main">-->
<div class="navbar">
    <div class="navbar-container container">
        <div class="navbar-logo">
            <div class="pull-left logo">
                <MainNavButton>
                    <img src="logo{colorScheme}.png" alt="logo{colorScheme}.png"/>
                </MainNavButton>
            </div>
        </div>
        <div id="navbar-collapse">
            <ul class="navbar-nav pull-right">
                <li class="active">
                    <SmoothA goto_id="home-hook">Welcome</SmoothA>
                </li>
                <li>
                    <SmoothA goto_id="services">We Offer</SmoothA>
                </li>
                <li>
                    <SmoothA goto_id="about"> Our Shop</SmoothA>
                </li>
                <li>
                    <SmoothA goto_id="portfolio"> Special</SmoothA>
                </li>
                <li>
                    <SmoothA goto_id="team"> Chef Team</SmoothA>
                </li>
                <li>
                    <SmoothA goto_id="contact"> Get In Touch</SmoothA>
                </li>
            </ul>
        </div>
    </div>
</div>
<!--</div>-->

<style>
    .navbar {
        /*position: fixed;*/
        padding: 1px 0;
        top: 0;
        right: 0;
        left: 0;
        z-index: 1030;
        background-color: var(--second-background-color);
        border-color: #080808;
        border-color: rgba(127, 90, 5, 1);
        border-width: 0 0 1px;
    }

    .navbar-container {
        width: 100% !important;
        justify-content: space-between;
        @media (max-width: 660px) {
            justify-content: center;
        }
        @media (min-width: 1150px) {
            justify-content: space-around;
        }
    }

    .navbar-nav > li {
        position: relative;
        display: block;
        float: left;

        margin: 3px;
        padding-left: 10px;
        padding-right: 10px;
        border-radius: 5px;
        background-color: var(--little-background-color);
    }

    #navbar-collapse {
        margin-right: 25px;
        margin-left: 0;

        @media (max-width: 566px) {
            display: none;
        }
    }

    .navbar-nav {
        display: flex;

        @media (max-width: 566px) {
            flex-direction: column;
        }
    }

    .logo {
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 10px;
        padding-left: 15px;
    }

    .container {
        width: 100%;
        padding-right: 15px;
        padding-left: 15px;
        margin-right: auto;
        margin-left: auto;

        display: flex;
        align-items: center;

        @media (min-width: 1200px) {
            width: 1170px;
        }
        @media (min-width: 992px) {
            width: 970px;
        }
        @media (min-width: 768px) {
            width: 750px;
        }
    }

    @media (max-width: 885px) {
        #navbar-collapse {
            margin-right: 0;
        }

        .navbar-nav {
            padding-left: 0;
            margin-top: 0;
        }

        .navbar-container {
            padding: 0;
            flex-direction: column;
            justify-content: flex-start;
        }

        .logo {
            padding-left: 0;
            margin-bottom: 0;
        }
    }
</style>