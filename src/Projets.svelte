<script>
    import { fade } from 'svelte/transition';
</script>

<div in:fade>    
    <h2> Projects</h2>
    <div>
        <div class="title">
            <h3>Portofolio </h3>
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

            <ul class="projects">

            </ul>
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

    h3 {
        font-size: 2rem;
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

</style>