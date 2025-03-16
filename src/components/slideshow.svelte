<script>


    const images = [
        "favicon.png",
        "furro.gif",
        "Untitled.jpg"
    ]
    let i = 0

    function nextPhoto(){
      i = (i + 1) % images.length
    }
    function prevPhoto(){
      i = (i - 1) % images.length;
    }
    function AutoSlide(){
      setInterval(nextPhoto, 3000);
    }
    AutoSlide();
</script>


<div class = "gallery" >
  <div class = "image-container" style="transform: translateX({-100 * i}%);">
{#each images as img}
    <img src={`/${img}`} alt={img} loading="lazy" class = "slide"/>
{/each}
  </div>
</div>
<style>
  
  :root {
        --image-size: clamp(150px, 30vw, 400px);
    }
    .gallery {
      display: flex;
      gap: 10px;
      flex-direction: column;
      width: var(--image-size);
      aspect-ratio: 1 / 1;

      overflow: hidden;
    }
    .image-container {
      width: 100%;
      display: flex;
      transition: transform 0.5s;

    }

  
    .slide {
      width: var(--image-size);
      aspect-ratio: 1 / 1;
      flex-shrink: 0;
    }
  
</style>