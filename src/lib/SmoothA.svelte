<script lang="ts">
    export let goto_id: string;

    const handleClick = () => {
        const element = document.getElementById(goto_id);
        if (!element) {
            console.warn(`Element with id ${goto_id} not found!`);
            return;
        }
        element.scrollIntoView({behavior: 'smooth'});
    };

    const onKeydown = (e: KeyboardEvent) => {
        if (e.key === 'Enter') handleClick();
    }

    const onKeyup = (e: KeyboardEvent) => {
        if (e.key === 'Space') handleClick();
    }

</script>

<div class="smoothA" on:click={handleClick} tabindex="0" role="button" on:keydown={onKeydown} on:keyup={onKeyup} {...$$restProps}>
    <slot/>
</div>

<style>
    .smoothA {
        width: 100%;
        cursor: pointer;
        text-decoration: none;
        color: var(--text-color);
        text-align: center;
    }
</style>