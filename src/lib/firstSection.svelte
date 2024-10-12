<script>
  let images = [
    { src: "assets/image-33.jpg", alt: "Image 1" },
    { src: "assets/image-9.jpg", alt: "Image 2" },
    { src: "assets/image-16.jpg", alt: "Image 3" },
    { src: "assets/image-18.jpg", alt: "Image 4" },
    { src: "assets/image-14.jpg", alt: "Image 14" },
    { src: "assets/image-31.jpg", alt: "Image 31" },
    { src: "assets/image-5.jpg", alt: "Image 3" },
    { src: "assets/image-6.jpg", alt: "Image 4" },
  ];

  let selectedImageIndex = 0;

  function setMainImage(index) {
    selectedImageIndex = index;
  }
</script>

<section class="gallery">
  <h2>INTRODUCTION</h2>
  <div class="container">
    <div class="text-content">
      <p>
        It all started with a friendly challenge. My neighbor, who had his eye on a plot of land behind our apartment,
        wanted to plant maize<span>&#127805;</span> and cassava<span>&#129364;</span> with spinach and okro along. One
        day, while chatting, he casually asked why I hadn’t used the little space behind my apartment to grow something
        myself. Honestly, I’d always thought about starting a garden but had never taken the plunge. I told him if I
        were to plant anything, it would be tomatoes<span>&#127813;</span>, peppers<span>&#127798;</span>, okro and any
        other vegetables<span>&#129362;</span> that I find interesting. Even though we both had interest in farming, the
        rising cost of food and the pressing need for more affordable options was one of the main reasons. It wasn’t just
        us feeling the pinch—food prices in Nigeria had skyrocketed, making even basic meals a challenge for many households.
      </p>
    </div>

    <div class="main-image">
      <img src={images[selectedImageIndex].src} alt={images[selectedImageIndex].alt} />
    </div>
    <div class="thumbnail-container" style="--width:150px; --height:250px; --quantity:8">
      <div class="thumbnail-image-wrapper">
        {#each images as image, index}
          <div
            class="thumbnail"
            style="--position: {index}"
            on:click={() => setMainImage(index)}
            class:selected={index === selectedImageIndex}
          >
            <img src={image.src} alt={image.alt} />
          </div>
        {/each}
      </div>
      <p>click on any of the image</p>
    </div>
  </div>
</section>

<style>
  .gallery {
    max-width: 500px;
    margin: 0 auto;
    padding: 0 2rem;
  }

  h2 {
    font-size: 1.85rem;
    font-weight: 900;
    color: #ff8c00;
  }

  .container {
    display: grid;
    /* flex-direction: column; */
    grid-template-columns: 1fr;
    grid-template-areas:
      "text"
      "main"
      "thumbnails";
  }

  /* .text-content,
  .main-image,
  .thumbnail-container {
    width: 100%;
  } */

  .main-image {
    /* width: 100%; */
    height: 300px; /* Fixed height for consistency */
    margin-bottom: 4px;
  }

  .main-image img {
    width: 100%;
    height: 100%;
    border-radius: 1rem;
    box-shadow: rgba(0, 0, 0, 0.4) 0px 30px 90px;
    object-fit: cover;
  }

  .thumbnail-container {
    grid-area: thumbnails;
    justify-self: center;
    width: 75%;
    margin: 2rem auto;
    overflow: hidden;
    padding: 0 1rem;
    box-shadow:
      rgba(255, 255, 255, 0.1) 0px 1px 1px 0px inset,
      rgba(50, 50, 93, 0.25) 0px 50px 100px -20px,
      rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
    border-radius: 10px;
  }

  .thumbnail-container p {
    text-align: center;
    font-family: "Kalam";
    font-weight: 600;
  }

  .thumbnail-image-wrapper {
    /* display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 4px; */

    /* height: 100px; Fixed height for consistency */
    /* width: 75%; */

    display: flex;
    gap: 4px;
    width: 100%;
    min-width: calc(var(--width) * var(--quantity));
    position: relative;
    height: 75px;
  }

  .thumbnail {
    /* flex: 1;
    cursor: pointer;
    transition: filter 0.3s ease; */
    aspect-ratio: 2 / 1;
    cursor: pointer;
    /* width: 100%; */

    /* testing out animation */
    width: var(--width);
    /* height: var(--height); */
    position: absolute;
    left: 100%;
    transition: filter 0.5s;
    animation: autoRun 10s linear infinite;
    animation-delay: calc((8.25s / var(--quantity)) * (var(--position) - 1));
  }

  @keyframes autoRun {
    from {
      left: 100%;
    }
    to {
      left: calc((var(--width)) * -1);
    }
  }

  .thumbnail img {
    width: 100%;
    height: 100%;
    box-shadow: rgba(0, 0, 0, 0.45) 0px 25px 20px -20px;
    border-radius: 8px;
    object-fit: cover;
    transition: filter 0.3s ease;
  }

  .thumbnail:not(.selected) img {
    filter: grayscale(100%);
  }

  .text-content {
    grid-area: text;
  }

  .main-image {
    grid-area: main;
  }

  /* Media query for larger screens */
  @media (min-width: 790px) {
    .gallery {
      max-width: 850px;
      margin: 0 auto;
      padding: 0 6rem;
    }

    .container {
      /* flex-wrap: wrap;
      flex-direction: row; */

      grid-template-columns: 65% 35%;
      grid-template-areas:
        "text main"
        "thumbnails thumbnails";
    }

    .main-image {
      height: 400px; /* Taller on larger screens */
    }

    /* .thumbnail-container .thumbnail-image-wrapper {
      padding-top: 2rem;
    } */

    .text-content p {
      padding-right: 6rem;
    }

    /*  
    .text-content {
      flex: 0 0 35%;
      order: 1;
    }

     .main-image {
      flex: 0 0 65%;
      order: 2;
      height: 400px;
    }

      */
  }
</style>
