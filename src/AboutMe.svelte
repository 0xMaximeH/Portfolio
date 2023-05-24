<script>
    
    import Typewriter from 'svelte-typewriter';
    import { fade,scale } from "svelte/transition";
    import { inview } from 'svelte-inview';

    let isInView;
    let isInViewSkill;
    const options = {
        rootMargin: '-200px',
        unobserveOnEnter: true,
    };
</script>

<div>
    <section> 
        <div>
            <Typewriter mode={"cascade"}>
                <h1> <span>Hello, I am </span> <span class="orange"> Maxime</span>.</h1>
            </Typewriter>
            

            <p id="description" in:fade="{{delay: 600 }}"> 
                I'm a Software Engineer from France.
            <br>
               I love to discover new technologies and learn new things.
            </p>
        </div>

        <div id="wall-container" in:fade="{{delay: 800 }}">
            <div id="wallpaper"/>
        </div>
    </section>
    
   
    <section use:inview={options} on:inview_enter={(event) => {
        isInView = event.detail.inView; 
      }} in:fade="{{delay:200}}" >

        {#if isInView}
        
            <h2 in:fade> Which language do I speak ? </h2>
            
            <div id="skill-container" in:fade="{{delay:100}}" use:inview={options} on:inview_enter={(event) => {
                isInViewSkill = event.detail.inView; 
            }} >
                {#if isInViewSkill}
                <div class="skill" in:scale="{{delay:100}}">
                    <div class="skill-title">
                        <img class="logo" alt="Svelte logo" src="src\assets\skills\Svelte.svg"/>
                        <h4> Front-End </h4>
                    </div>
                    <p> HTML / CSS / JS 
                        <br>
                        I develop most of the time with <strong>Svelte </strong> and  <strong>React</strong>. 
                        <br> Small experience with Angular.
                    </p>
                </div>

                <div class="skill" in:scale="{{delay:200}}">
                    <div class="skill-title">
                        <img class="logo" alt="Git logo" src="src\assets\skills\Git.svg"/>
                        <h4> General </h4>
                    </div>
                    <p> UML / Git / Design pattern / Project management / API REST / French / </p>
                </div>

                <div class="skill" in:scale="{{delay:300}}"> 
                    <div class="skill-title">
                        <img class="logo" alt="Symfony logo" src="src\assets\skills\Symfony.svg"/>
                        <h4> Back-End </h4>
                    </div>
                    <p> PHP Symfony / C#.NET / ExpressJS / SQL
                        and Database Management
                    </p>
                </div>
                {/if}
            </div>
            <div id="skill-image" >
                <img in:fade="{{delay:400}}" alt="arrivalBackground" id="skill-bg" src="src\assets\ArrivalWomanWalking.webp"/>
                <div class="end-bg dark-bg">

                </div>
            </div>
        {/if}
    </section>

    <section class="dark-bg">
        <h2> Experience </h2>
        <div id="jobs">
            <div class="job"> 
                <h3>2018-2022</h3>                   
                
                <div class="job-description">
                    <div class="job-tilte"> 
                        <span class="orange"> Software Developer </span>
                        <span> - CreditMutuel </span>
                     </div> 
                    <p> Credit Mutuel is a major banking and insurance group in France.
                            Developed an app to manage top ups and buyouts of contract of both
                        intern and external insurance company.
                            Improving the efficiency of the departement to identify error
                        on insurance contract by redesign the data visulation tool and
                        by creating a batch program. Prevented hundred of incident tickets.
                        Worked in collaboration with a team in Singapore team for a part of the 
                        developement. </p>
                        
                        <div>
                            <div class="genres"
                                style:--color='#061c23'>
                                <span>C#</span>
                            </div>
                            <div class="genres"
                                style:--color='#9a5229'>
                                <span>Cobol</span>
                            </div>
                        </div>
                </div>
                
            </div>
            <div class="job"> 
                <h3>2018 -  6months</h3>
                <div class="job-description">

                    <div class="job-tilte"> 
                        <span class="orange"> Intern Software Developer </span> 
                        <span> - Incotec Software </span>
                     </div>
                    <p> Incotec Software develop application for time management and HR departement. 
                        Created a database architecture visualization and modifiction tool 
                        to help the team identify column in their hundred of tables.    
                    </p>

                    <div>
                        <div class="genres"
                            style:--color='#061c23'>
                            <span>C#</span>
                        </div>
                        <div class="genres"
                            style:--color='#829ba2'>
                            <span>Angular</span>
                        </div>
                    </div>
                </div>
            </div>
           
        </div>
    </section>
    
</div>

<style>
    
    h1 {
        font-size: 5rem;
        margin: 3rem;
    }

    h2 {
        font-size: 3rem;
        padding: 1em;
        margin: 0;
    }

    #description {
        line-height: 1.8;
        font-size: 1.5rem;
        text-align: center;
        margin: 1.5rem 0 1.5rem;
        font-weight: bold;
    }

    .logo {
        display: inline-block;
        width: 60px;
        fill: #132b30;
    }

    h4 {
        padding-left: 10px;
        font-size: 1.7rem;
        margin: 30px 0;
        color: #132b30;
        display: inline-block;
    }    

    .skill-title {
        display: flex;
        align-items: center;
    }

    #skill-container {
        position: relative;
        display: flex;
        border: 0.7rem solid transparent;
        background: linear-gradient(
            50deg,
            hsl(18deg 68% 41%) 0%,
            hsl(18deg 68% 44%) 5%,
            hsl(18deg 68% 47%) 9%,
            hsl(18deg 70% 51%) 14%,
            hsl(18deg 80% 54%) 18%,
            hsl(18deg 92% 57%) 23%,
            hsl(18deg 100% 63%) 27%,
            hsl(18deg 100% 70%) 32%,
            hsl(18deg 100% 77%) 36%,
            hsl(17deg 100% 84%) 41%,
            hsl(16deg 90% 90%) 45%,
            hsl(240deg 9% 96%) 50%,
            hsl(204deg 10% 81%) 55%,
            hsl(200deg 10% 67%) 59%,
            hsl(198deg 10% 53%) 64%,
            hsl(197deg 14% 40%) 68%,
            hsl(196deg 26% 27%) 73%,
            hsl(195deg 37% 20%) 77%,
            hsl(195deg 37% 19%) 82%,
            hsl(195deg 37% 18%) 86%,
            hsl(195deg 38% 17%) 91%,
            hsl(195deg 38% 15%) 95%,
            hsl(196deg 38% 14%) 100%
            ) border-box;
        max-width: 1100px;
        border-radius: 30px;
        width: 100%;
        margin: auto;
        height: 333px;
        box-shadow: 0 4px 30px rgba(0, 0, 0, 0.2);
        z-index: 3;
    }

    .end-bg {
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 204px;
        box-shadow: -10px -25px 20px 30px #061a20;
        z-index: -2;
    }

    #skill-bg {
        position: relative;
        width: 800px;
        height: 500px;
        object-position: 50% 50%;
        bottom: 0px;
        top: -90px;
        opacity: 1;
        filter: blur(4px);
        padding: 1rem;
        object-position: 0% -100%;
        object-fit: cover;
        border: none;
        border-radius: 35px;
    }

    .dark-bg {
        background-color: #061a20;
        color: #f3f3f5;
    }
    
    #skill-image {
        position: relative;
        text-align: center;
    }

    .skill {
        width: 33%;
        border: 0.7rem solid transparent;
        border-radius: 30px;
        padding: 30px 30px;
        background-color: #f9fbfc;
        background-clip: padding-box;
    }

    .skill > p {
        margin-left: 10px;
        font-size: 19px;
        border-radius: 16px;
    }
    
    #wallpaper {    
        top: 35%;
        left: 0;
        background-image: url("src/assets/ArrivalDiscovery.jpg");
        background-size: cover;
        background-repeat: no-repeat;
        background-position: 0% 30%;
        height: 100%;
        width: 100%;
        border: none;
        border-radius: 15px;
        box-shadow: rgba(100, 100, 111, 0.2) 15px 7px 10px 0px,rgba(100, 100, 111, 0.2) 5px -7px 5px 0px;    
    }

    #wall-container {
        position: relative;
        height: 600px;
        max-width: 1200px;
        margin: auto;       
    }

    #jobs {
        display: grid;
        gap: 30px;
        grid-template-columns: repeat(1fr,1fr);
        padding: 30px;        
    }

    .job {
        display: flex;
        background: rgba(255, 255, 255, 0.05);
        border-radius: 16px;
        box-shadow: 0 4px 30px rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(25.2px);
        -webkit-backdrop-filter: blur(25.2px);
        border: 1px solid rgba(255, 255, 255, 0.1);
        margin: auto;
        width: 800px;
        
    }

    .job > h3 {
        font-size: 2rem;
        width: 30%;
    }
    
    .job-description  {
        padding: 2rem;
        line-height: 1.5;
        width: 60%;
    }

    .job-tilte {        
        font-size: 1.5rem;        
        font-weight: bold;
    }

    .genres {
        display: inline-block;
        overflow: hidden;
        font-family: "Segoe UI";
        font-size: 16px;
        border-radius: 4px;
        margin: 2px;
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