<script lang="ts">
    import Navbar from "./lib/Navbar.svelte";
    import Greeting from "./lib/Greeting.svelte";
    import {setContext} from 'svelte';

    const handleThemeChange = () => {
        const isInDarkMode = window.matchMedia('(prefers-color-scheme: dark)').matches;
        document.body.classList.toggle('dark-mode', isInDarkMode);
        document.body.classList.toggle('light-mode', !isInDarkMode);
        document.documentElement.style.setProperty('--text-color', isInDarkMode ? '#c1bdc7' : 'black');
        document.documentElement.style.setProperty('--little-background-color', isInDarkMode ? '#313131' : '#e7e7e7');
        document.documentElement.style.setProperty('--background-color', isInDarkMode ? '#222' : 'white');
        document.documentElement.style.setProperty('--second-background-color', isInDarkMode ? '#2b2b2b' : '#ececec');
        document.documentElement.style.setProperty('--third-background-color', isInDarkMode ? '#3b3b3b' : '#b2b2b2');
    }

    window.matchMedia("(prefers-color-scheme: dark)").addEventListener("change", handleThemeChange);
    handleThemeChange();
    setContext('isMobile', true);
</script>

<div id="home-hook"></div>
<main>
    <Navbar/>
    <Greeting/>
</main>
