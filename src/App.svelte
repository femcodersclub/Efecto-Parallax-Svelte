<script>
  import { Parallax, ParallaxLayer } from "svelte-parallax";
  import BackgroundGradientAnimation from './components/BackgroundGradientAnimation.svelte';

  const handleDestroy = () => {
    console.log('Componente destruido');
  }

  let parallax;
  let disabled = false;
  let femCodersClub = "femCoders Club".split(""); 
  let src = "/femcoders.jpg";
</script>

<BackgroundGradientAnimation onDestroy={handleDestroy} />

<Parallax sections={3} bind:this={parallax} {disabled}>
  {#each femCodersClub as char, index (index)} 
    <ParallaxLayer
    rate={(index + 1) / (femCodersClub.length - 1)}
    offset={1}
    style="
      background-color: transparent;
      margin-left: {18 + index * 5}%; 
      font-size: 2rem; 
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5); 
      color: white; 
    "
    >
      <p class="femCoders Club">
        {char}
      </p>
    </ParallaxLayer>
  {/each}

  <ParallaxLayer
    offset={1}
    rate={-2.5}
    style="display: flex; justify-content: flex-end;"
  >
    <div
      style="background-color: lightblue; opacity: 0.5; width: 50%; height: 100%;"
    />
  </ParallaxLayer>

  <ParallaxLayer
    offset={1}
    rate={2.5}
    style="display: flex; justify-content: flex-start;"
  >
    <div
      style="background-color: yellow; opacity: 0.5; width: 50%; height: 100%;"
    />
  </ParallaxLayer>

  <ParallaxLayer
  rate="1"
  style="
    background-color: transparent; 
    display: flex; 
    justify-content: center; 
    align-items: center; 
    flex-direction: column;
  "
>
  <h1 class="title">
    Efecto Parallax con Svelte
  </h1>

  <div class="buttons-container">
  
    <button
      class="bottom-btn"
      on:click={() => parallax.scrollTo(3, { selector: ".top-btn", duration: 4000 })}
    >
      Click me!
    </button>

    <button
      class="disable"
      on:click={() => (disabled = !disabled)}
    >
      disable
    </button>
  </div>

  <img {src} alt="Image description" aria-hidden="true" style="" />
</ParallaxLayer>

<ParallaxLayer
  offset="2"
  rate="2"
  style="
    background-color: pink; 
    display: flex; 
    justify-content: center; 
    align-items: center;
  "
>
  <button
  class="bottom-btn"
    on:click={() =>
      parallax.scrollTo(1, { selector: ".bottom-btn", duration: 1000 })}
  >
    Scroll to top
  </button>
</ParallaxLayer>
</Parallax>

<style>
img {
  margin-top: 50px;
  width: 100%;
  height: auto;
}
</style>

