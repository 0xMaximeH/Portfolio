<script>
    import Films from './movies/Films.svelte';
    import Projets from './Projets.svelte';
    import AboutMe from './AboutMe.svelte';
    import { fly } from "svelte/transition";

    export let selectedTab = AboutMe;
    
    let previousY = 0;
	let currentY = 0;
	let clientHeight;

    const deriveDirection = (y) => {
		const direction = !previousY || previousY < y ? 'down' : 'up';
		previousY = y;

		return direction;
	}
    
	$: scrollDirection = deriveDirection(currentY); 
    $: offscreen = scrollDirection === 'down' && currentY > clientHeight;
    

</script>

<svelte:window bind:scrollY={currentY} />

<header in:fly="{{ y: 75, duration: 900 }}" class:hide={offscreen} bind:clientHeight >
    <div class="head">
        <h1> 
            <a on:click={() => selectedTab = AboutMe} href="/">
                Ox<span class="orange">Maxime</span> 
            </a>
        </h1>

        <nav>
            <ul>
                <li> 
                    <button style:--color={'#365669'} on:click={() => selectedTab = AboutMe}> 
                        About 
                    </button>
                </li>
                <li> 
                    <button style:--color={'#9c2436'} on:click={() => selectedTab = Films}>
                        Movies
                    </button>
                </li>
                <li> 
                    <button style:--color={'#163d76'} on:click={() => selectedTab = Projets}> 
                        Projets 
                    </button>
                </li>
            </ul>
        </nav>
  </div>
</header>

<style>
    
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@400;700;900&family=Open+Sans:wght@600&display=swap');
.hide {
  transform: translateY(-100%);
}

ul {
    list-style: none;
    display: flex;
    gap: 1vw;
    justify-content: flex-end;
    padding-right: 2vw;
    background: transparent;
    
}

button {
    position: relative;
    display: inline-block;
    text-decoration: none;
    border: none;
    font-family: "Georgia";
    font-size: 1.25em;
    font-weight: bold;
    color: black;
    background: transparent;    
}

button:hover {
    color: transparent;
    background-color:var(--color);
    background-size: 100%;
    background-repeat: no-repeat;
    cursor: pointer;
    background-clip: text;
    -webkit-background-clip: text;
    transition: all .4s;
    transform: scale(1.05);
}

a {
    text-decoration: none;
}
a:visited {
    color: black;
}

header {    
    background-color: #f3f3f5;
    /* background-color: transparent;*/
    transition: top 0.2s ease-in-out;
    transition: transform 100ms linear;
    position: sticky;
    width: 100%;
    top: 0;
    z-index: 9;
}

.head {
    display: flex;
    justify-content: space-between;
    width: 100%;
    align-items: center;
    font-weight: 700;
    max-width: 1200px;
    margin: auto;
}

header::after {
    content: "";
    position: absolute;
    left: 0;
    width: 100%;
    height: 0.5rem;
    background: linear-gradient( to bottom, rgba(0, 0, 0, .1) 0%, rgba(0, 0, 0, .05) 30%, transparent 100% );
}

h1 {
    font-size: 1.7rem;
    padding-left: 2rem;
}


</style>