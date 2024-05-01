<!-- Banner.svelte -->
<script>
    // Importa las bibliotecas necesarias
    import { createEventDispatcher } from 'svelte';
  
    // Define las propiedades del componente
    export const type = "info";
    export let dismissable = true;
    export let title = "¡Únete a femCoders Club!";
    export let subtitle = "Conéctate con mujeres apasionadas por la tecnología y participa en eventos, talleres y charlas inspiradoras.";
    export let actionText = "¡Únete!";
    export let actionHref = "https://femcodersclub.com/";
  
    // Crea un dispatcher de eventos
    const dispatch = createEventDispatcher();
  
    // Función para manejar el evento de cierre del banner
    function handleClose() {
      dispatch('close');
    }
  </script>
  
  <div class="banner" class:dismissable={dismissable}>
    <!-- Contenido del banner -->
    <div class="banner-content">
      <h2>{title}</h2>
      <p>{subtitle}</p>
      <a href={actionHref} class="banner-button">{actionText}</a>
    </div>
  
    <!-- Botón para cerrar el banner si es dismissable -->
    {#if dismissable}
      <button class="close-button" on:click={handleClose}>Cerrar</button>
    {/if}
  </div>
  
  <style>
    /* Estilos del banner */
    .banner {
      background-color: #007bff;
      color: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
  
    .banner-content {
      flex: 1;
    }
  
    .banner-button {
      background-color: white;
      color: #007bff;
      padding: 10px 20px;
      border-radius: 4px;
      text-decoration: none;
    }
  
    .close-button {
      background-color: transparent;
      border: none;
      color: white;
      cursor: pointer;
      font-size: 1rem;
    }
  </style>
  
  
  
  