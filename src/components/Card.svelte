<script>
  export let imageUrl;
  export let title;
  export let description;
</script>

<div class="card">
  <div class="card-content">
    <div class="card-front">
      <img src={imageUrl} alt={title} />
    </div>
    <div class="card-back">
      <h2>{title}</h2>
      <p>{description}</p>
    </div>
  </div>
</div>

<style>
  .card {
    perspective: 1000px;
    width: 100%;
    height: 300px;
    position: relative;
    margin-bottom: 20px;
  }

  .card-content {
    width: 100%;
    height: 100%;
    transition: transform 0.5s;
    transform-style: preserve-3d;
    position: relative;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  }

  .card:hover .card-content {
    transform: rotateY(180deg);
  }

  .card-front,
  .card-back {
    width: 100%;
    height: 100%;
    position: absolute;
    backface-visibility: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
    border-radius: 10px;
  }

  .card-front {
    background: linear-gradient(45deg, #e16b29, #3f3a8a, #e16b29, #3f3a8a);
  }

  .card-back {
    background-color: rgba(255, 220, 220, 0.5);
    backdrop-filter: blur(10px);
    transform: rotateY(180deg);
    display: flex;
    flex-direction: column;
  }

  img {
    max-width: 100%;
    max-height: 100%;
    border-radius: 10px;
  }

  p {
    font-size: 1rem;
    color: #3f3a8a;
  }
</style>
