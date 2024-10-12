<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
  let isVisible = false;

  function handleSwitch() {
    isVisible = !isVisible;
    dispatch("onSwitch", { message: isVisible });
  }
</script>

<div class="switcher">
  <button on:click={handleSwitch}>
    <div class="switcher-mobile">
      <img class="logo" src="assets/bush.png" alt="claude logo" />
      <span class="arrow"
        ><svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="lucide-icon lucide lucide-chevron-right"><path d="m9 18 6-6-6-6"></path></svg
        ></span
      >
    </div>
    <div class="switcher-desktop svelte-28km66">
      <span>Read Claude’s story</span>
      <span class="arrow svelte-28km66"
        ><svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="lucide-icon lucide lucide-chevron-right"><path d="m9 18 6-6-6-6"></path></svg
        ></span
      >
    </div></button
  >
</div>

<style>
  button {
    padding: 8px;
    height: 4rem;
    /* display: -webkit-box; */
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    font-size: 18px;
    border: 4px solid black;
    border-right: 0px;
    background: #ff8c00;
    color: white;
    pointer-events: auto;
    white-space: nowrap;
    -webkit-transition: background calc(1s * 0.3);
    transition: background calc(--1s * 0.3);
  }

  .switcher-mobile {
    display: flex;
    height: 100%;
    -webkit-box-align: center;
    align-items: center;
  }

  .logo {
    height: 100%;
    display: block;
    max-width: 100%;
  }

  .arrow {
    margin: 0 6px;
  }

  .switcher-desktop {
    display: none;
  }
</style>
