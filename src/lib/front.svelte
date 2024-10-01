<script>
  export let title = "Jayeola Garden Visual Story";
  export let description = "Your description goes here";
</script>

<div class="fullscreen">
  <div class="content">
    <h1>{title}</h1>
    <p>{description}</p>
  </div>
  <div class="scroll-down">
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
    background-color: #f0f0f0;
    position: relative;
  }

  .content {
    text-align: center;
    padding: 20px;
    max-width: 80%;
  }

  h1 {
    font-size: 3rem;
    margin-bottom: 1rem;
  }

  p {
    font-size: 1.2rem;
  }

  .scroll-down {
    position: absolute;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%);
    animation: bounce 2s infinite;
  }

  .arrow {
    width: 30px;
    height: 30px;
    border: solid #333;
    border-width: 0 3px 3px 0;
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
  }
</style>
