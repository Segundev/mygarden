<script>
  import FrontPage from "./lib/front.svelte";
  import Paragraph from "./lib/section.svelte";
  import Chart from "./lib/sectionChart.svelte";
  import Rect from "./lib/sectionRect.svelte";
  import FirstSection from "./lib/firstSection.svelte";
  import Fp from "./lib/fp.svelte";
</script>

<main>
  <FrontPage />
  <article>
    <FirstSection />
    <Paragraph />
    <Rect />
    <Chart />
    <Paragraph />
    <Paragraph />
  </article>
</main>

<style>
  article {
    padding-top: 4rem;
  }
  /* article {
    position: relative;
    z-index: 1; 
  }

  article::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: url("assets/noise.png");
    background-size: contain;
    opacity: 0.1; 
    z-index: -1; 
    pointer-events: none; 
  } */
</style>
