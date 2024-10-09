<script>
  export let title = "I Made My First Garden";
  export let description = "I decided to make a garden and this is what I have. Nothing much but I learnt a lot";
</script>

<div class="fullscreen">
  <div class="content">
    <h1>{title}</h1>
    <p>{description}</p>
  </div>
  <div class="scroll-down">
    <img src="assets/vase.png" alt="" />
    <div class="arrow"></div>
  </div>
</div>

<style>
  .fullscreen {
    height: 100vh;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: #092e09;
    background-image: url("assets/DesktopBG.jpg");
    background-size: contain;
    color: #ffffff;
    position: relative;
  }

  p {
    color: white;
  }

  .content {
    text-align: center;
    padding: 20px;
    max-width: 80%;
  }

  .scroll-down {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    align-items: center;
    justify-content: center;
    position: absolute;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%);
    /* animation: bounce 1s infinite; */
  }

  .scroll-down img {
    width: 100px;
    height: 100px;
  }

  .arrow {
    width: 10px;
    height: 10px;
    border: solid #161616;
    border-width: 0 5px 5px 0;
    transform: rotate(45deg);
  }

  @keyframes bounce {
    0%,
    20%,
    50%,
    80%,
    100% {
      transform: translateY(0) translateX(-50%);
    }
    40% {
      transform: translateY(-20px) translateX(-50%);
    }
    60% {
      transform: translateY(-10px) translateX(-50%);
    }
  }

  @media (max-width: 768px) {
    h1 {
      font-size: 2rem;
    }

    p {
      font-size: 1rem;
    }

    .arrow {
      width: 20px;
      height: 20px;
    }

    .fullscreen {
      background-size: cover;
    }
  }
</style>
