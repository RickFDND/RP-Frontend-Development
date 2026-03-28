<script>
  import Line from "$lib/components/atoms/Line.svelte";
</script>

<section class="text-image-block">
  <h2>What Do We <span>Focus</span> On?</h2>

  <div class="content">
    <p>
      <strong>RP Frontend Development</strong> specializes in building custom
      websites that are not only visually appealing, but also technically
      excellent in performance. We focus on four fundamental pillars:
      <strong>responsiveness</strong>, <strong>accessibility</strong>,
      <strong>performance</strong>
      and <strong>progressive enhancement</strong>. Every website we deliver is
      built with these core principles in mind. Our design is clean, minimalist
      and purposeful. We believe in quality over quantity and deliver solutions
      that truly work for your audience, on every device and accessible to
      everyone.
    </p>
    <img src="/image.png" alt="" width="350" />
  </div>
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 100vh;
    gap: 1rem;
    padding-block: var(--section-padding);
    padding-inline: 1.5rem;

    h2 {
      span {
        color: var(--color-accent);
      }
    }

    .content {
      display: flex;
      flex-direction: column;
      gap: 5rem;

      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
      }

      @media (min-width: 900px) {
        display: grid;
        grid-template-columns: 1fr 1fr;
      }
    }

    @media (min-width: 668px) {
      padding-inline: 10%;
    }
  }
</style>
