<div class="sectionRect">
  <p>
    It all started with a friendly challenge. My neighbor, who had his eye on a plot of land behind our apartment,
    wanted to plant maize, cassava, spinach, and okra. One day, during a casual chat, he asked why I hadn’t used the
    little space behind my apartment to grow something myself.
  </p>
</div>

<style>
  .sectionRect {
    position: relative;
    margin: 0 auto;
    padding: 2rem;
    max-width: 700px;
  }

  .sectionRect p {
    border: 4px solid black;
    padding: 1rem;
    max-width: 550px;
    text-align: center;
    background-color: #ff4500;
    color: white;
    margin: 0 auto;
  }

  .sectionRect::before {
    content: "";
    position: absolute;
    top: -5%;
    left: 9%;
    width: 75px;
    height: 75px;
    background-image: url("assets/bush.png");
    background-size: contain;
    z-index: 1;
  }
</style>
