<script>
    import { fly } from 'svelte/transition';
    
    import MovieDetail from './MovieDetail.svelte';
    import { movies } from "../assets/movies.js";
    let detail = false;
    let movie = movies[0];

</script>

<section>
    <div class="center" in:fly="{{ y: 95, duration: 600 }}">
        <p id="like"> Because who doesn't like movies? </p>
        <a target="_blank" href="https://letterboxd.com/0xmaxime/">
            <p id="letterbox">
                <span>Follow </span><span>me on </span><span>Letterboxd</span>
            </p>
        </a>    
    </div>
    
    <h2 in:fly="{{ y: 75, duration: 900 }}">
        Favourite films
    </h2>

    <div id="favoris">

        {#each movies as card, i }
            <button on:click={() => {detail = true; movie = card;}}> 
            <div class="card"
            in:fly="{{ y: 75, duration: 1000, delay: 50*i }}"
            style:color={card.color} 
            style:background-image={"url("+card.imageUrl+")"}
            style:font-family={card.font}
            style:--color={card.shadowColor}
            
            >
                <h4>{card.genre}</h4>
            </div>
        </button>
        {/each}
    
    </div>
</section>

{#if detail}
    <MovieDetail bind:detail={detail} movie={movie} />
{/if}
<style>

    @font-face {
        font-family:"kepler-std-semicondensed-dis";
        src:url("https://use.typekit.net/af/78897f/000000000000000000012f83/27/l?primer=7cdcb44be4a7db8877ffa5c0007b8dd865b3bbc383831fe2ea177f62257a9191&fvd=n7&v=3") format("woff2"),url("https://use.typekit.net/af/78897f/000000000000000000012f83/27/d?primer=7cdcb44be4a7db8877ffa5c0007b8dd865b3bbc383831fe2ea177f62257a9191&fvd=n7&v=3") format("woff"),url("https://use.typekit.net/af/78897f/000000000000000000012f83/27/a?primer=7cdcb44be4a7db8877ffa5c0007b8dd865b3bbc383831fe2ea177f62257a9191&fvd=n7&v=3") format("opentype");
        font-display:auto;font-style:normal;font-weight:700;font-stretch:normal;
    }
    
    #like {
        font-size: 1.3rem;
    }

    h4 {
        font-weight: 600;
        font-size: 25px;
    }

    h2 {
        color: #061c23;
        font-size: 2rem;
        padding: 0.5em;
        margin: 1rem;
    }
    
    #favoris {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 32px;
        max-width: 950px;
        z-index: 1;
        margin: auto;
    }

    .card { 
        background-size: cover;
        background-blend-mode: darken;
        box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.05),
                    0px 8px 15px rgba(0, 0, 0, 0.1),
                    0 0 0 1px rgba(255, 255, 255, 0.1);
        padding: 16px;
        border-radius: 15px;
        cursor: pointer;
        transition: box-shadow .25s;
        width: 12rem;
        height: 19rem;
    }

    .card:hover {
        box-shadow: 0px 3px 6px var(--color),
                    0px 15px 25px var(--color),
                    0 0 0 2px var(--color);
        transition: all .4s;
        transform: scale(1.02);
    } 

    #letterbox:hover > span {
        text-decoration: underline;
        text-decoration-thickness: 1.5px;
    }

    a {
        text-decoration: none;
        font-size: large;
        font-weight: bold;
    }

    #letterbox > span:nth-child(1) {
        color: #ff8000;
    }
    #letterbox > span:nth-child(2) {
        color: #00e054;
    }
    #letterbox > span:nth-child(3) {
        color: #40bcf4;
    }
    #letterbox > span:nth-child(4) {
        color: #40bcf4;
    }



</style>