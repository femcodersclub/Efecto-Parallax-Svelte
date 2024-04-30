<script>
  export let imageUrl; 
  export let title; 
  export let description; 
</script>

<div class="card">
  <img src={imageUrl} alt={title} />
  <h3>{title}</h3>
  <p>{description}</p>
</div>

<style>
    .card {
    background-color: rgba(255, 255, 255, 0.332);
    border-radius: 10px;
    padding: 30px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    width: 100%;
    -webkit-backdrop-filter: blur(10px);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    margin-bottom: 20px;
  }
  img{
    width: 400px;
  }
</style>













  