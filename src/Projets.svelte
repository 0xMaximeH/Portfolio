<script>
    import { fade } from 'svelte/transition';
</script>

<div in:fade>    
    <h2> Projects</h2>
    <div>
        <div class="title">
            <h4>
                Portfolio
            </h4>
           
            <div class="center">
                <div class="genres"
                    style:--color='#ff3e00'>
                    <span>Svelte</span>
                </div>
                <div class="genres"
                    style:--color='#242628'>
                    <span>Mux Player</span>
                </div>
            </div>
        </div>
        
        <div class="slider">

            <ul class="projects">
                <li class="project" style='background-image: url("projects/Movies.jpg");'>
                    
                </li>

                <li class="project" style='background-image: url("projects/Portfolio.jpg");'>
                    
                </li>

                <li class="project" style='background-image: url("projects/Skill.jpg");'>

                </li>

            </ul>
        </div>
    </div>

    <div>
        <div class="title">
            <h3>WebOSTV App in construction </h3>
        </div>
        <div class="slider">
            <ul class="projects"></ul>
        </div>
    </div>    
    
</div>

<style>
    .slider {
        position: relative;
        display: flex;
        text-align: center;
        margin: auto;
        padding-left: 30px;
        max-width: 1330px;
        max-height: 30vh;
        height: 30vh;
    }

    h4 {
        font-size: 1.5rem;
        margin: 1rem;
    }

    .projects {
        display: flex;
        flex-wrap: wrap;
        list-style: none;
        gap: 30px;
        
        scroll-behavior: smooth;
        scrollbar-width: none; 
        -ms-overflow-style: none;
    }

    ul::-webkit-scrollbar { 
        width: 0;
        height: 0;
    }
    
    .project {
        position: relative;
        display: flex;
        min-width: 40vh;
        height: 100%;
        background-image: url("public/Portfolio.PNG");
        background-size: cover;
        background-position: 25%;
        border: none;
        border-radius: 20px;
        
    }

    .project::before {
        position: absolute;
        content: "";
        height: 100%;
        width: 100%;
        inset: 0;
        opacity: 0.2;
        border-radius: 20px;
        background: linear-gradient(rgba(0, 0, 0, 0.1) 10%, rgba(0, 0, 0, 0.78) 80%)
    }


    .genres {
        display: inline-block;
        text-align: start;
        overflow: hidden;
        font-family: "Segoe UI";
        font-size: 16px;
        border-radius: 4px;
        margin: 5px;
        border: 1px solid var(--color);
        box-shadow: 2px 1px 10px rgba(255, 254, 254, 0.2);
        background-color: var(--color);
    }
    
    .genres > span {
        display: block;
        padding: 7px 15px;
        width:100%;
        font-weight: 500;
        color: white;
        user-select: none;
    }
    
</style>