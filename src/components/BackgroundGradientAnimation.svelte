<script>
  export let onDestroy;

  function handleMouseMove(event) {
    const x = event.clientX / window.innerWidth;
    const y = event.clientY / window.innerHeight;
    const gradient = `linear-gradient(${x * 360}deg, #e16b29, #3f3a8a)`;

    backgroundStyle = gradient;
  }

  let backgroundStyle = "";

  window.addEventListener("mousemove", handleMouseMove);

  onDestroy(() => {
    window.removeEventListener("mousemove", handleMouseMove);
  });
</script>

<main>
  <div class="background" style="background-image: {backgroundStyle}"></div>
</main>
