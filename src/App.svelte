<script>
  import FrontPage from "./lib/front.svelte";
  import Chart from "./lib/sectionChart.svelte";
  import Rect from "./lib/sectionRect.svelte";
  import Aside from "./lib/Aside.svelte";
  import Switcher from "./lib/Switcher.svelte";
  import FirstSection from "./lib/firstSection.svelte";
  import Footer from "./lib/footer.svelte";

  let isVisible = false;
</script>

<div class="outer">
  <div class="inner" class:visible={isVisible}>
    <div class="switcher"><Switcher on:onSwitch={(e) => (isVisible = e.detail.message)} /></div>
    <main>
      <FrontPage />
      <article>
        <FirstSection />
        <section>
          <p>
            The prices of local food commodities like tomatoes, peppers, and other vegetables were so expensive that
            recipes requiring a lot of tomatoes and peppers were avoided in favor of alternative soup<span
              >&#129367;</span
            > ingredients. Rice, which is a major part of our meals, doubled in price, as did beans, which are heavily relied
            upon as a source of protein to prevent meals from being entirely energy-based.
          </p>
        </section>
        <Rect />
        <Chart />
        <section>
          <p>
            Though the idea of growing my own food intrigued me, the thought of actually starting felt overwhelming.
            Fortunately, my dad came for a visit around that time. A seasoned farmer in his youth, he still had all the
            skills. With his help, we cleared the bushes and prepared the ridges, leaving me with one task—planting. But
            as life would have it, I procrastinated.
          </p>

          <p>
            Then, my neighbor—who had challenged me—came by to plant okra, ewedu, and efo (spinach). All I needed was to
            ask him for some okro and efo seedlings. That’s how my journey as a gardener began.
          </p>
        </section>
        <section>
          <h2>Planting Tomato and Pepper</h2>
          <p>
            After planting both the okro and efo, I had a challenge with rain. Rain was very sparse during may. The
            early year ended soon around early april and by June, the ground was very hard has they were was no rain.
            This affected my efo seeding, on a normal day, it should take about a week to two and it would start
            sprouting but it took about 6 weeks before I started seeing signs of growth. I even cleared some of it when
            weeding when the weeds started fillng the group
          </p>
          <p>
            After planting the okro and efo, my farm buddy recommended a place where I could get good-quality seedlings
            of various plant types. A week later, I visited the spot and booked a dozen tomato and fresh pepper
            seedlings. After waiting for about 6 to 7 weeks, I finally got the call—my seedlings were ready for pickup.
          </p>
          <p>
            I was told of two options if I wanted to transplant the seedling. I could just transpant it directly to my
            farm, normal land or I could prepare plant pot. I had to get cemt bags, wash it and filled it with filtered
            soil, removing stones and debris.
          </p>
          <div class="image-container">
            <div class="image-wrapper one">
              <img src="/assets/image-5.jpg" alt="" srcset="" />
            </div>
            <div class="image-wrapper two">
              <img src="/assets/image-6.jpg" alt="" srcset="" />
            </div>
            <!-- <div class="image-wrapper three">
          <img src="/assets/image-5.jpg" alt="" srcset="" />
        </div> -->
          </div>
          <p>
            After planting, I was told to apply fungicides after two weeks and wet the plant every day. Did this for
            about a month, and my plants started growing, fruiting exellently well with green leaves so large my
            neighbours questioning me if this was actually a pepper.
          </p>
          <p>
            After planting, I was told to apply fungicides after two weeks and wet the plant every day. Did this for
            about a month, and my plants started growing, fruiting exellently well with green leaves so large my
            neighbours questioning me if this was actually a pepper.
          </p>
          <p>
            After about 12 weeks, my tomato began fruiting, likewise my pepper. But some of the tomato were seen to be
            bad. One of the reason was due to lack of calcium, I had to go get calcium and some wood to tie the tomato
            branch to the wood, so the tomato leaves and fruit doesnt touch the floor, part of the reason for the
            infection
          </p>
        </section>
        <section>
          <h2>Harvest Time!</h2>
          <p>
            A few days ago, I harvested my first crops. I couldn’t wait for the tomatoes to ripen fully, so I picked
            them while they were still a little green. As for the okra, I’ve left some to mature and harden so I can use
            the seeds for next year’s planting. The efo has started making seeds too, and I’m hoping these will sprout
            faster than the original batch.
          </p>
        </section>
        <section>
          <h2>The Unseen Challenges</h2>
          <p>
            Of course, gardening comes with its share of challenges. Birds and rodents have become regular visitors to
            my little farm. Even after cultivating, the battle against pests continues.
          </p>
        </section>
      </article>
      <Footer />
    </main>
    <div class="side">
      <Aside />
    </div>
  </div>
</div>

<style>
  .outer {
    overflow: hidden;
  }

  .switcher {
    top: 10vh;
    transform: translateY(-50%);
    left: auto;
    right: calc(100% - 100vw);
    position: fixed;
    z-index: 1000;
  }

  .inner {
    display: flex;
    height: 100vh;
    width: max-content;
    transform: translate(0);
    transition:
      transform calc(1s * 0.5) ease-in-out,
      -webkit-transform calc(1s * 0.5) ease-in-out;
  }

  .inner.visible {
    transform: translate(-92vw);
  }

  main {
    width: 96vw;
    overflow-y: scroll;
    flex-shrink: 0;
  }

  .side {
    width: 96vw;
    overflow-y: scroll;
    flex-shrink: 0;
  }

  article {
    padding-top: 4rem;
  }

  section {
    margin: 0 auto;
    padding: 0 2rem;
    max-width: 700px;
  }

  .image-container {
    position: relative;
    width: 200px;
    height: 300px;
    margin: 50px auto;
  }

  .image-wrapper {
    position: absolute;
    top: 0;

    width: 100%;
    height: 100%;
    transform: rotate(0deg);
    /* transition: transform 0.3s ease; */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }

  .image-wrapper.one {
    transform: rotate(5deg);
    left: 70px;
  }

  .image-wrapper.two {
    transform: rotate(346deg);
    top: 20px;
  }

  /* .image-wrapper:hover {
    transform: rotate(5deg) translateY(-10px);
    z-index: 10;
  } */

  .image-wrapper img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 8px;
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
