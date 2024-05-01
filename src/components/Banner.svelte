<script>
  import { createEventDispatcher } from 'svelte';

  export const type = "info";
  export let dismissable = true;
  export let title = "¡Únete a femCoders Club!";
  export let subtitle = "Conéctate con mujeres apasionadas por la tecnología y participa en eventos, talleres y charlas inspiradoras.";
  export let actionText = "¡Únete!";
  export let actionHref = "https://communityinviter.com/apps/femcodersclub/femcoders-club";

  const dispatch = createEventDispatcher();

  function handleClose() {
    dispatch('close');
  }
</script>

<div class="banner" class:dismissable={dismissable}>
  <div class="banner-content">
    <div>
      <h2>{title}</h2>
      <h3>{subtitle}</h3>
    </div>
    <div>
      <a href={actionHref} class="banner-button">{actionText}</a>
    </div>
  </div>
</div>

<style>
  .banner {
    width: 100%;
    padding: 20px;
    border-radius: 8px;
    background: linear-gradient(45deg, #e16b29, #3f3a8a, #e16b29, #3f3a8a);
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
    position: absolute; 
    top: 0; 
    left: 0; 
    overflow: hidden; 
  }

  .banner-content {
    display: flex;
    flex-direction: column; 
    justify-content: center;
    align-items: center;
    animation: slideLeft 15s linear infinite; 
  }

  h2, h3 {
    color: white;
    margin: 20px; 
    text-align: center;
  }

  .banner-button {
    background: linear-gradient(45deg, #e16b29, #3f3a8a, #e16b29, #3f3a8a);
    color: white;
    padding: 10px 20px;
    border-radius: 10px;
    text-decoration: none;
    transition: background-color 0.3s ease;
    margin-top: 10px; 
  }

  .banner-button:hover {
    background-color: #0056b3;
  }

  @keyframes slideLeft {
    0% {
      transform: translateX(-100%);
    }
    100% {
      transform: translateX(100%);
    }
  }
</style>








