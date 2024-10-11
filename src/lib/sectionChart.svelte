<script>
  import { onMount } from "svelte";

  onMount(() => {
    const flourishScript = document.createElement("script");
    flourishScript.src = "https://public.flourish.studio/resources/embed.js";
    flourishScript.async = true;
    document.body.appendChild(flourishScript);
  });
</script>

<section>
  <h3>Prices of Goods and Services have Increased rapidly in last 2years</h3>
  <div class="flourish-embed flourish-chart" data-src="visualisation/19721541">
    <!-- <script src="https://public.flourish.studio/resources/embed.js" async></script> -->
  </div>
</section>

<style>
  section {
    margin: 0 auto;
    padding: 2rem;
    max-width: 700px;
  }

  /* .flourish-embed {
    height: 500px;
  } */
</style>
