<script lang="ts">
    import SmoothA from "./SmoothA.svelte";
    import {getContext, onMount} from 'svelte';

    let isMobile: boolean = getContext('isMobile');
    let isOpinionsVisible: boolean = document.body.clientWidth > 566;

    window.addEventListener('resize', () => {
        isOpinionsVisible = document.body.clientWidth > 566;
        console.log(`Is mobile: ${isMobile}, is opinions visible: ${isOpinionsVisible}`)
        const navbar = document.getElementById("navbar-collapse");
        navbar.style.display = isOpinionsVisible ? '' : 'none';
    })
    const handleClick = () => {
        const navbar = document.getElementById("navbar-collapse");
        navbar.style.display = navbar.style.display !== 'none' ? 'none' : 'inherit';
    }

    onMount(() => {
        const navbar = document.getElementById("navbar-collapse");
        navbar.style.display = isOpinionsVisible ? '' : 'none';
    })
    console.log(`Is mobile: ${isMobile}, is opinions visible: ${isOpinionsVisible}`)
</script>

{#if isMobile && !isOpinionsVisible}
    <button on:click={handleClick}>
        <slot/>
    </button>
{:else}
    <SmoothA goto_id="home-hook">
        <slot/>
    </SmoothA>
{/if}

<style>
    button {
        margin: 0;
        padding: 0;
        border: 0;
        background: none;

        width: 100%;
        cursor: pointer;
        text-decoration: none;
        color: var(--text-color);
        text-align: center;
    }
</style>