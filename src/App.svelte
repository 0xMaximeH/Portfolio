<script>
    import { setContext } from 'svelte';
    import Header from './Header.svelte';
    import { writable } from 'svelte/store';
    
    let allmovies = writable([]);
    let allgenres = writable([]);
    setContext('movies', allmovies);
    setContext('genres', allgenres);
    
    let selectedTab;

</script>

    <!-- <link rel="stylesheet" href="https://use.typekit.net/rbf8fzv.css">-->

    <Header bind:selectedTab/>

    <main>
        <svelte:component this={selectedTab}/>
    </main>

<style>
    /*
    box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.04),
                    0px 15px 25px rgba(0, 0, 0, 0.3),
                    0 0 0 2px var(--color);
    */
</style>