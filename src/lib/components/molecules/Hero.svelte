<script>
  import Button from "$lib/components/atoms/Button.svelte";
</script>

<section class="hero-section">
  <div>
    <h1>Evaluate Your <span>Digital</span> Presence</h1>
    <p>
      Crafting exceptional web experiences that blend cutting-edge technology
      with sophisticated design.
    </p>
    <Button href="/contact">Start your project</Button>
  </div>
</section>

<style>
  .hero-section {
    background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
      url(/image.png);
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    background-color: var(--color-secondary);
    height: clamp(280px, 20vw + 30vh, calc(100vh - 80px));
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    div {
      animation: fadeInUp 0.8s ease-out forwards;
      opacity: 0;
      padding-inline: 1.5rem;

      h1 {
        margin: 0;
        color: var(--color-primary);
        font-size: clamp(2rem, 7vw, 11rem);

        span {
          color: var(--color-accent);
        }
      }

      p {
        margin-block-start: 0.5em;
        margin-block-end: 1.17em;
        color: var(--color-muted);
      }

      @media (min-width: 668px) {
        padding-inline: 10%;
      }
    }

    @media (min-width: 1024px) and (max-height: 1000px) {
      height: calc(100vh - 80px);
    }
  }

  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
</style>
