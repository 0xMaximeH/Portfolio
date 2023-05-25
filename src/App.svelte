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

    <Header bind:selectedTab/>

    <main>
        <svelte:component this={selectedTab}/>
    </main>

<style>

</style>