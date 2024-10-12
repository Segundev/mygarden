<script>
  // Generate an array of 40 image objects with the correct naming convention
  const images = Array(40)
    .fill()
    .map((_, i) => ({
      src: `/assets/image-${i + 1}.jpg`,
      alt: `Image ${i + 1}`,
    }));

  let containerWidth;

  $: columns = getColumnCount(containerWidth);

  function getColumnCount(width) {
    if (width < 600) return 2;
    if (width < 900) return 3;
    return 4;
  }
</script>

<div class="grid-container" bind:clientWidth={containerWidth}>
  {#each images as { src, alt }, i}
    <div class="grid-item" style="grid-row: span {1 + (i % 3)};">
      <img {src} {alt} />
    </div>
  {/each}
</div>

<style>
  .grid-container {
    display: grid;
    gap: 8px;
    width: 100%;
    padding: 8px;
  }

  .grid-item {
    break-inside: avoid;
    position: relative;
    overflow: hidden;
  }

  .grid-item::before {
    content: "";
    display: block;
    padding-top: 150%; /* 2:3 aspect ratio */
  }

  img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  @media (max-width: 599px) {
    .grid-container {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  @media (min-width: 600px) and (max-width: 899px) {
    .grid-container {
      grid-template-columns: repeat(3, 1fr);
    }
  }

  @media (min-width: 900px) {
    .grid-container {
      grid-template-columns: repeat(4, 1fr);
    }
  }
</style>
