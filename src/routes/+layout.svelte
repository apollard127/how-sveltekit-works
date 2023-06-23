<script>
    import '$lib/app.css'
    import Header from "$lib/Header.svelte";
    import MobileHeader from "$lib/MobileHeader.svelte";
    import Footer from "$lib/Footer.svelte"; 


let innerWidth
</script>

<svelte:window bind:innerWidth />
<div class="wrapper">
    {#if innerWidth > 767}
<Header logo="My Fun Science"/>
{:else}
<Header logo="MFS"/>
{/if}

<main class="flow">
<slot />
</main>
<Footer />
</div>

<style>
    .wrapper {
        min-height: 100dvh;
        display: grid;
        grid-template-rows: auto 1fr auto;
    }
    main {
        width:  100%;
        max-width: var(--max-width);
        padding-block: 6em; 
        padding-inline: 3em;
        margin-inline: auto;
        line-height: 1.5;
    }
</style>