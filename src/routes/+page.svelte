<script>
  import Header from "$lib/components/organisms/Header.svelte";
  import Hero from "$lib/components/molecules/Hero.svelte";
  import TextImageBlock from "$lib/components/templates/Text-Image-Block.svelte";
</script>

<Header />
<Hero />
<TextImageBlock />

<main class="animation-container">
  <div class="card-container">
    <section>
      <h2>huts</h2>
    </section>
    <section>
      <h2>doei</h2>
    </section>
    <section>
      <h2>hallo</h2>
    </section>
    <section>
      <h2>hoi</h2>
    </section>
  </div>
</main>

<style>
  .card-container {
    position: sticky;
    top: 0;

    section {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100svh;
      width: 100vw;
    }

    section:nth-of-type(1) {
      background-color: blue;
    }
    section:nth-of-type(2) {
      background-color: red;
    }
    section:nth-of-type(3) {
      background-color: pink;
    }
    section:nth-of-type(4) {
      background-color: lightblue;
    }
  }

  @supports (animation-timeline: --container) {
    .animation-container {
      height: 200vh;
      overflow: clip;
      view-timeline-name: --container;

      .card-container {
        display: flex;
        width: 400vw;
      }

      section {
        position: sticky;
        left: 0;

        animation-timeline: --container;
        animation-fill-mode: both;
        animation-range: cover 100vh exit 1%;
        animation-name: scrollanimation;
      }
    }

    @keyframes scrollanimation {
      0% {
        transform: translateX(0);
      }

      33% {
        transform: translateX(-100vw);
      }

      66% {
        transform: translateX(-200vw);
      }

      100% {
        transform: translateX(-300vw);
      }
    }
  }
</style>
