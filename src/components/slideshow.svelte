<script>


    const images = [
        "furro.gif",
        "bea.png",
        "sonic.jpg",
        

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
<style lang="scss">
  
  
  :root {
        --image-width: clamp(150px, 30vw, 900px);
    }
    .gallery {
      margin: 0 auto;
      display: flex;
      gap: 10px;
      flex-direction: column;
      width: var(--image-width);
      aspect-ratio: 16 / 9;

      overflow: hidden;
    }
    .image-container {
      width: 100%;
      display: flex;
      transition: transform 0.5s;

    }

  
    .slide {
      width: var(--image-width);
      aspect-ratio: 16 / 9;
      flex-shrink: 0;
    }
  
</style>