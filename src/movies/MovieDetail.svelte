<script>
    import MuxPlayer from './MuxPlayer.svelte';  
    export let detail;
    export let movie;

    import { fade } from "svelte/transition";
</script>

<div in:fade="{{duration: 150 }}">
    <div on:click={() => { detail = false;console.log(detail)}} id="overlay"/>

    <div class="container" style:--bgcolor={movie.backgroundColor} >
        <div class="detail-img center">
            <div class="cardo"
                
                style:color={movie.color} 
                style:background-image={"url("+movie.imageUrl+")"}
                style:font-family={movie.font}                
                >
            </div> 
        </div>
        <div class="movie-detail"> 
            <p> <span class="label"> Title :</span> {movie.title} </p>
        
            <p> <span class="label"> Film director :</span> {movie.director} </p>
            <p> <span class="label"> Genres :</span> {movie.genre} </p>
            <p> <span class="label"> Description :</span> </p>
            <p> {movie.description} </p>
            <span class="label"> Trailer: </span>
            <MuxPlayer />
        </div>
        
        
    </div>
</div>

<style>

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

    #overlay {
        width: 100%;
        height: 100%;
        opacity: 0.8;
        background-color: black;
        position: absolute;
        top: 0;
    }

    .container {
        position: absolute;
        display: flex;
        align-items: center;
        top: 50%;
        left: 50%;
        min-height: 50vh;
        min-width: 90vh;
        transform: translate(-50%, -50%);
        border: 1px solid #ffffff;
        background-color: var(--bgcolor);
        color: snow; 
        padding: 30px 0;
        border-radius: 15px;
    }    

    .detail-img {
        display: inline-block;
        width: 40%;
    }

    .movie-detail {
        opacity: 1;
        display: inline-block;
        position: relative;
        width: 50%;
        left: 10px;
    }

    .label {
        font-size: 1em;
        font-weight: bolder;
    }  

</style>