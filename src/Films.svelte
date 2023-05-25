<script>
    import { fly } from 'svelte/transition';
    import MuxPlayer from './MuxPlayer.svelte';  

    let cards = [
    {genre:"THRILLER", font:"Joane Stencil Regular // Sensaway", shadowColor:"#163d76",color:"#fefffe", imageUrl:"movies//Burning.jpg"},
    {genre:"SCI-FI", font:"'Lato', sans-serif", color:"#596871",shadowColor:"#7899b3", imageUrl:"movies/Arrival.jpg"},  
    {genre:"HORROR", font:"kepler-std-semicondensed-dis, serif", shadowColor:"#9c2436",color:"#fbedda", imageUrl:"movies/Raw.jpg"},
    {genre:"Drama", font:"Helvetica", color:"#f2f3ec",shadowColor:"#9d2324", imageUrl:"movies/Aftersun.jpg"},
    {genre:"ACTION", font:"Arial", color:"#c9bd99 ",shadowColor:"#745e43", imageUrl:"movies/Madmax.jpg"}
  ]
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

        {#each cards as card, i }
            <div class="card"
            in:fly="{{ y: 75, duration: 1000, delay: 50*i }}"
            style:color={card.color} 
            style:background-image={"url("+card.imageUrl+")"}
            style:font-family={card.font}
            style:--color={card.shadowColor}
            >
                <h4>{card.genre}</h4>
            </div>
        {/each}
    
    </div>
</section>

<!-- Example -->
<section>
    <h2>
        (In construction) Detail of movie 
    </h2>
    <div class="container">
        <div class="detail-img center">
            <div class="cardo"
                
                style:color={cards[0].color} 
                style:background-image={"url("+cards[0].imageUrl+")"}
                style:font-family={cards[0].font}
                style:--color={cards[0].shadowColor}
                >
                
                    <!--<h4>{cards[0].genre}</h4> -->
            </div> 
        </div>
        <div class="movie-detail"> 
            <p> <span class="label"> Title :</span> Burning </p>
        
            <p> <span class="label"> Film director :</span> Lee Chang-dong</p>
            <p> <span class="label"> Genres :</span> Thriller </p>
            <p> <span class="label"> Description :</span> </p>
            <p> Jong-su bumps into a girl who used to live in the same neighborhood,
                who asks him to look after her cat while she's on a trip to Africa.
                When back, she introduces Ben, a mysterious guy she met there, who
                confesses his secret hobby.
            </p>
            <span class="label"> Trailer: </span>
            <MuxPlayer />
        </div>
        
        
    </div>
</section>

<style>

    @font-face {
        font-family:"kepler-std-semicondensed-dis";
        src:url("https://use.typekit.net/af/78897f/000000000000000000012f83/27/l?primer=7cdcb44be4a7db8877ffa5c0007b8dd865b3bbc383831fe2ea177f62257a9191&fvd=n7&v=3") format("woff2"),url("https://use.typekit.net/af/78897f/000000000000000000012f83/27/d?primer=7cdcb44be4a7db8877ffa5c0007b8dd865b3bbc383831fe2ea177f62257a9191&fvd=n7&v=3") format("woff"),url("https://use.typekit.net/af/78897f/000000000000000000012f83/27/a?primer=7cdcb44be4a7db8877ffa5c0007b8dd865b3bbc383831fe2ea177f62257a9191&fvd=n7&v=3") format("opentype");
        font-display:auto;font-style:normal;font-weight:700;font-stretch:normal;
    }

    .center {
        text-align: center;
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
    }  

    .cardo { 
        position: relative;
        display: inline-block;
        margin: 0;
        background-size: cover;
        padding: 16px;
        border-radius: 15px;
        width: 16.5rem;
        height: 25rem;
    }

    .detail-img {
        display: inline-block;
        position: relative;
        width: 40%;
        vertical-align: top;
        top: 100px;
    }

    .movie-detail {
        display: inline-block;
        position: relative;
        width: 50%;
        left: 10px;
    }

    .label {
        font-size: 1em;
        font-weight: bolder;
    }

    .container {
        margin-top: 2rem;
        max-width: 1200px;
        margin: auto;
        background-color: #163d76;
        color: #f3f3f5; 
        padding: 30px 0;
        font-size: medium;
        border-radius: 15px;
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