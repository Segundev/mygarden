<script>
  import { onMount } from "svelte";

  // Image data with src and alt text
  // Array of 42 image objects
  const images = Array(12)
    .fill()
    .map((_, i) => ({
      src: `/assets/image-${i + 1}.jpg`,
      alt: `Image ${i + 1}`,
    }));

  let gridContainer;
  let columns = 3; // Default number of columns
  let visibleImages = [];
  let loading = true;
  let error = null;

  function updateGrid() {
    const containerWidth = gridContainer.offsetWidth;
    columns = Math.floor(containerWidth / 250); // Adjust 250 to change minimum column width
    columns = Math.max(1, Math.min(columns, 5)); // Ensure columns are between 1 and 5
  }

  function loadImages() {
    loading = true;
    error = null;
    visibleImages = images.map((img) => ({ ...img, loaded: false }));

    Promise.all(
      visibleImages.map(
        (img) =>
          new Promise((resolve, reject) => {
            const image = new Image();
            image.onload = () => {
              img.loaded = true;
              resolve();
            };
            image.onerror = () => reject(new Error(`Failed to load ${img.src}`));
            image.src = img.src;
          })
      )
    )
      .then(() => {
        loading = false;
      })
      .catch((e) => {
        error = e.message;
        loading = false;
      });
  }

  onMount(() => {
    updateGrid();
    loadImages();
    window.addEventListener("resize", updateGrid);
    return () => window.removeEventListener("resize", updateGrid);
  });
</script>

<svelte:window on:resize={updateGrid} />

<div bind:this={gridContainer} class="grid-container" style="--columns: {columns};">
  {#if loading}
    <p>Loading images...</p>
  {:else if error}
    <p class="error">{error}</p>
  {:else}
    {#each visibleImages as image (image.src)}
      <div class="grid-item">
        {#if image.loaded}
          <img src={image.src} alt={image.alt} />
        {:else}
          <div class="placeholder">Loading...</div>
        {/if}
      </div>
    {/each}
  {/if}
</div>

<style>
  .grid-container {
    display: grid;
    grid-template-columns: repeat(var(--columns), 1fr);
    padding: 4px;
    height: 100vh;
    width: 100vw;
    overflow: auto;
  }

  .grid-item {
    aspect-ratio: 1;
    overflow: hidden;
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    filter: grayscale(100%);
    transition: transform 0.3s ease;
  }

  img:hover {
    transform: scale(1.05);
  }

  .placeholder {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #f0f0f0;
    color: #888;
  }

  .error {
    color: red;
    text-align: center;
  }
</style>
