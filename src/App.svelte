<script>
  import { Parallax, ParallaxLayer } from "svelte-parallax";
  import BackgroundGradientAnimation from './components/BackgroundGradientAnimation.svelte';
  const handleDestroy = () => {
	  console.log('Componente destruido');
	}

  let parallax;
  let disabled = false;
  let fancy = "fancy".split("");
  let src = "/femcoders.jpg";
</script>

<BackgroundGradientAnimation onDestroy={handleDestroy} />
<button class="disable" on:click={() => (disabled = !disabled)}>disable</button>

<Parallax sections={3} bind:this={parallax} {disabled}>
  {#each fancy as char, index (index)}
    <ParallaxLayer
      rate={(index + 1) / (fancy.length - 1)}
      offset={1}
      style="
		  background-color: transparent;
			 margin-left: {38 + index * 5}%; 
				display: flex; 
				justify-content: flex-start; 
				align-items: center;
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
    <h1>Efecto Parallax con Svelte</h1>
    <button
      class="bottom-btn"
      on:click={() =>
        parallax.scrollTo(3, { selector: ".top-btn", duration: 4000 })}
    >
      Click me!
    </button>

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
      class="top-btn"
      on:click={() =>
        parallax.scrollTo(1, { selector: ".bottom-btn", duration: 1000 })}
    >
      Scroll to top
    </button>
  </ParallaxLayer>
</Parallax>

<style>
  :global(body) {
    padding: 0;
    background-color: white;
    color: #313131;
    font-family: monospace;
  }

  h1 {
    font-size: 2rem;
    margin-top: 180px;
  }

  button {
    font-size: 1rem;
    cursor: pointer;
  }

  button:focus {
    outline: 4px dashed #ff5c77;
  }

  .disable {
    position: fixed;
    top: 1rem;
    left: 1rem;
    z-index: 10;
  }

  img {
    margin-top: 50px;
    width: 100%;
    height: auto;
  }
</style>
