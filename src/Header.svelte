<script>
  import Films from './Films.svelte';
  import Projets from './Projets.svelte';
  import AboutMe from './AboutMe.svelte';

  export let selectedTab = AboutMe;
</script>

<header>
  <div class="head">
    <h1> Ox<span class="orange">Maxime</span> </h1>
    <nav>
      <ul>
        <li> <button style:--color={'#365669'} on:click={() => selectedTab = AboutMe}> About </button></li>
        <li> <button style:--color={'#9c2436'} on:click={() => selectedTab = Films}> Movies </button> </li>
        <li> <button style:--color={'#163d76'} on:click={() => selectedTab = Projets}> Projets </button> </li>
      </ul>
    </nav>
  </div>
</header>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@400;700;900&family=Open+Sans:wght@600&display=swap');
ul {
  list-style: none;
  display: flex;
  gap: 1vw;
  justify-content: flex-end;
  padding-right: 2vw;
}

button {
  position: relative;
  display: inline-block;
  text-decoration: none;
  border: none;
  font-family: "Georgia";
  font-size: 1.25em;
  font-weight: bold;
  background-clip: text;
  transition: background-color .3s ease-in-out;
  -webkit-background-clip: text;
}

a {
    text-decoration: none;
    color: none;
}

button:hover {
  color: transparent;
  background-color:var(--color);
  background-size: 100%;
  background-repeat: no-repeat;
  cursor: pointer;
  background-clip: text;
  -webkit-background-clip: text;
}

header {
  position: relative;
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