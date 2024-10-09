<script>
  let images = [
    { src: "assets/image-33.jpg", alt: "Image 1" },
    { src: "assets/image-9.jpg", alt: "Image 2" },
    { src: "assets/image-16.jpg", alt: "Image 3" },
    { src: "assets/image-18.jpg", alt: "Image 4" },
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
        wanted to plant maize and cassava with spinach and okro along. One day, while chatting, he casually asked why I
        hadn’t used the little space behind my apartment to grow something myself. Honestly, I’d always thought about
        starting a garden but had never taken the plunge. I told him if I were to plant anything, it would be tomatoes,
        peppers, okro and any other vegetables that I find interesting. Even though we both had interest in farming, the
        rising cost of food and the pressing need for more affordable options was one of the main reasons. It wasn’t
        just us feeling the pinch—food prices in Nigeria had skyrocketed, making even basic meals a challenge for many
        households.
      </p>
    </div>

    <div class="main-image">
      <img src={images[selectedImageIndex].src} alt={images[selectedImageIndex].alt} />
    </div>
    <div class="thumbnail-container">
      <div class="thumbnail-image-wrapper">
        {#each images as image, index}
          <div class="thumbnail" on:click={() => setMainImage(index)} class:selected={index === selectedImageIndex}>
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
    object-fit: cover;
  }

  .thumbnail-container {
    grid-area: thumbnails;
    justify-self: center;
    width: 65%;
  }

  .thumbnail-container p {
    text-align: center;
    font-family: "Kalam";
    font-weight: 600;
  }

  .thumbnail-image-wrapper {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 4px;

    /* height: 100px; Fixed height for consistency */
    /* width: 75%; */
  }

  .thumbnail {
    /* flex: 1;
    cursor: pointer;
    transition: filter 0.3s ease; */
    aspect-ratio: 1 / 1;
    cursor: pointer;
  }

  .thumbnail img {
    width: 100%;
    height: 100%;
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

    .thumbnail-container .thumbnail-image-wrapper {
      padding-top: 2rem;
    }

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
