<script>
  import { Parallax, ParallaxLayer } from "svelte-parallax";
  import BackgroundGradientAnimation from "./components/BackgroundGradientAnimation.svelte";
  import Card from "./components/Card.svelte";
  import Banner from "./components/Banner.svelte";
  import Footer from "./components/footer.svelte";

  const handleDestroy = () => {
    console.log("Componente destruido");
  };

  let parallax;
  let disabled = false;
  let femCodersClub = "femCoders Club".split("");
  let src = "/prueba.png";
</script>

<BackgroundGradientAnimation onDestroy={handleDestroy} />
<Parallax sections={3} bind:this={parallax} {disabled}>
  
  <ParallaxLayer offset={1} rate={0} style="width: 100%; height: 100%;">
    <video
      autoplay
      loop
      muted
      style="
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      z-index: -1;
    "
    >
      <source src="/femvideo.mp4" type="video/mp4" />
    </video>
  </ParallaxLayer>

  <ParallaxLayer offset={0} rate={0} style="width: 100%; height: 100%;">
    
    {#each femCodersClub as char, index (index)}
      <ParallaxLayer
        rate={(index + 1) / (femCodersClub.length - 1) / 2}
        offset={1}
        style="
          width: 50%;
          height: 100%;
          margin-left: {18 + index * 5}%; 
          font-size: 2rem; 
          text-shadow: 0 2px 4px rgba(0, 0, 0, 0.9);
          color: white; 
        "
      >
      
        <h3 class="femCoders Club">
          {char}
        </h3>
        
      </ParallaxLayer>
    {/each}
  </ParallaxLayer>

  <ParallaxLayer
    offset={1}
    rate={2.5}
    class="glass-section-right"
    style="width: 100%; height: 100%; "
  >
    <div class="glass-container-right">
      <h2 class="eventos-title" style="margin-top: 3rem;">Eventos</h2>
      <Card
        imageUrl="/evento1.jpeg"
        title="Más allá de la superficie🌈"
        description="En esta oportunidad, exploraremos estrategias esenciales para testear el backend y descubriremos los desafíos comunes en lo que respecta a la escalabilidad de los sistemas."
      />

      <Card
        imageUrl="/evento2.jpeg"
        title="Actitud mental y gestión emocional para ser lider de tu vida"
        description="👩‍💻Laure Jongejans Salinas nos ayudará a descubrir herramientas prácticas y consejos adaptados a cada realidad que nos ayudarán a alcanzar nuestras metas más ambiciosas!"
      />
    </div>
  </ParallaxLayer>

  <ParallaxLayer
    offset={1}
    rate={-2.5}
    class="glass-section-left"
    style="width: 100%; height: 100%; "
    
  >
    <div class="glass-container-left">
      <h2 class="pasados-title" style="margin-top: 3rem;">Pasados</h2>
      <Card
        imageUrl="/evento3.jpeg"
        title="Customiza Tu Perfil de GitHub 🚀💻"
        description="👩‍💻En este taller online, Mari Carmen Chueco Oviedo te guiará paso a paso para personalizar tu perfil de GitHub y hacerlo resaltar con tu estilo y creatividad."
      />

      <Card
        imageUrl="/evento4.jpeg"
        title="Celebrar a la mujer en tecnología en honor al Día Internacional de la Mujer! 💃🌐"
        description="Nos sumergiremos en el fascinante mundo de la tecnología junto a cuatro mujeres increíbles que están marcando la diferencia en este campo! 🌟👩‍💻"
      />
    </div>
  </ParallaxLayer>

  <ParallaxLayer
    rate="0.2"
    style="
      display: flex; 
      justify-content: center; 
      align-items: center; 
      flex-direction: column;
       
    "
  >
    <h1 class="title">Efecto Parallax con Svelte</h1>

    <div class="buttons-container">
      <button
        class="bottom-btn"
        on:click={() =>
          parallax.scrollTo(3, { selector: ".top-btn", duration: 4000 })}
      >
        Click me!
      </button>

      <button class="disable" on:click={() => (disabled = !disabled)}>
        Desactivar
      </button>
    </div>

    <div class="content-container">
      <div class="text-container">
        <h2>femCoders Club</h2>
        <p class="text-left">
          Un espacio donde las mujeres de todas las habilidades y trayectorias
          se unen para aprender, crecer y prosperar en el mundo de la
          tecnología.
        </p>
        <p class="text-left">
          Nuestro objetivo es derribar barreras, fomentar la diversidad y
          promover la igualdad de género en la industria.
        </p>
        <p class="text-left">
          ¡Únete a nosotros mientras construimos un futuro más inclusivo e
          innovador para todas! 😊
        </p>
      </div>

      <div class="logo-container">
        <img {src} alt="Logo" class="logo" />
      </div>
    </div>
  </ParallaxLayer>

  <ParallaxLayer
    offset="2"
    rate="1"
    style="
    display: flex; 
    justify-content: center; 
    align-items: center;
    
  "
  >
    <Banner />
    <video
      autoplay
      loop
      muted
      style="
      position: relative;
      top: 0;
      left: 0;
      width: 100%;
      object-fit:cover;
      z-index: -1;
    "
    >
      <source src="/cofundadoras.mp4" type="video/mp4" />
    </video>

    <button
      class="top-btn"
      style="  
      padding: 10px 20px; 
      border: none; 
      border-radius: 50%; 
      background: linear-gradient(45deg, #e16b29, #3f3a8a, #e16b29, #3f3a8a);
      color: white; 
      font-size: 1rem; 
      cursor: pointer; 
      transition: 0.3s;
      position: fixed;
      bottom: 9rem; 
      right: 20px;
    "
      on:click={() =>
        parallax.scrollTo(1, { selector: ".bottom-btn", duration: 1000 })}
    >
      Ir arriba👆
    </button>

    <Footer />
  </ParallaxLayer>
</Parallax>

<style>
  
</style>
