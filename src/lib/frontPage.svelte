<script>
  // Add your image paths here
  const images = [
    "/assets/image-1.jpg",
    "/assets/image-2.jpg",
    "/assets/image-3.jpg",
    "/assets/image-4.jpg",
    "/assets/image-5.jpg",
    "/assets/image-6.jpg",
    "/assets/image-7.jpg",
    "/assets/image-8.jpg",
    "/assets/image-9.jpg",
    "/assets/image-10.jpg",
    "/assets/image-11.jpg",
    "/assets/image-12.jpg",
    "/assets/image-13.jpg",
    "/assets/image-14.jpg",
    "/assets/image-15.jpg",
    "/assets/image-16.jpg",
    "/assets/image-17.jpg",
    "/assets/image-18.jpg",
    "/assets/image-19.jpg",
    "/assets/image-20.jpg",
    "/assets/image-21.jpg",
    "/assets/image-22.jpg",
    "/assets/image-23.jpg",
    "/assets/image-24.jpg",
    "/assets/image-25.jpg",
    "/assets/image-26.jpg",
    "/assets/image-27.jpg",
    "/assets/image-28.jpg",
    "/assets/image-29.jpg",
    "/assets/image-30.jpg",
    "/assets/image-31.jpg",
    "/assets/image-32.jpg",
    "/assets/image-33.jpg",
    "/assets/image-34.jpg",
    "/assets/image-35.jpg",
    "/assets/image-36.jpg",
    "/assets/image-37.jpg",
    "/assets/image-38.jpg",
    "/assets/image-39.jpg",
    "/assets/image-40.jpg",
    "/assets/image-41.jpg",
    "/assets/image-42.jpg",
    // Add more image paths as needed
  ];
</script>

<div class="grid-container">
  {#each images as image}
    <div class="grid-item">
      <img src={image} alt="Grid image" />
    </div>
  {/each}
</div>

<style>
  :global(body, html) {
    margin: 0;
    padding: 0;
    height: 100%;
    overflow: hidden;
  }

  .grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    grid-auto-rows: 1fr;
    height: 100vh;
    width: 100vw;
  }

  .grid-item {
    overflow: hidden;
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    filter: grayscale(100%);
  }
</style>
