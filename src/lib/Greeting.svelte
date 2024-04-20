<script lang="ts">
    import SmoothA from "./SmoothA.svelte";
</script>

<div id="greeting">
    <header class="clearfix tb">
        <div class="tb-cell text-center">
            <i class="fa fa-heart-o icon"></i>
            <h1>Coffee - Makes you Love</h1>
            <p>A Lot Can Happen Over Coffee, Its Awesome!!! </p>
            <SmoothA goto_id="portfolio" class="btn btn-lg">Today's Special</SmoothA>
        </div>
    </header>
</div>

<style>
    #greeting {
        width: 100%;
        padding-top: 150px;
        text-align: center;
        background: url("header_bg.jpg") no-repeat left;
        background-size: cover;
        background-position: left center;

        min-height: 850px;
    }

    #greeting p {
        color: #fff;
        font-size: 22px;
        font-weight: 300;
        text-align: center;
        letter-spacing: 1px;
    }

    #greeting .icon {
        color: #ffffff;
        margin-top: 115px;
        padding-bottom: 30px;
        letter-spacing: 8px;
        font-size: 100px;
        font-weight: bold;
    }
    #greeting h1 {
        font-family: "Raleway", serif;
    }

    #greeting .btn {
        font-weight: 500;
        font-size: 20px;
        margin: 50px 0;
        background-color: #e89a2f;
        color: #fff;
        border-radius: 0;
        color: #000;
    }

    @media (max-width: 650px) {
        #greeting {
            background-position: -130px 0;
        }
    }

    @media (min-width: 1570px) {
        #greeting {
            background-image: url("header_bg-large.jpg");
        }
    }
</style>