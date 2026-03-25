<script>
  import HamburgerMenu from "$lib/components/HamburgerMenu.svelte";
  import CloseMenu from "$lib/components/CloseMenu.svelte";
  import Button from "$lib/components/Button.svelte";
</script>

<header>
  <a href="/" class="logo">
    <img src="/logo-white.png" alt="" width="150" height="62.75" />
  </a>
  <nav id="nav-open">
    <ul>
      <li>
        <Button href="/" variant="ghost" size="md">Home</Button>
      </li>
      <li>
        <Button href="/about-us" variant="ghost" size="md">About us</Button>
      </li>
      <li>
        <Button href="/projects" variant="ghost" size="md">Projects</Button>
      </li>
      <li>
        <Button href="/contact" variant="ghost" size="md">Contact</Button>
      </li>
    </ul>
  </nav>
  <HamburgerMenu />
  <CloseMenu />
</header>

<style>
  header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 12vh;
    background-color: var(--color-secondary);
    position: relative;

    .logo {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 1rem;
    }

    nav {
      display: none;
      justify-content: center;
      align-items: center;

      ul {
        display: flex;
        justify-content: space-around;
        align-items: center;
        padding: 0;
        list-style-type: none;
        gap: 2rem;
      }

      @media (min-width: 800px) {
        display: flex;
        padding: 2rem;
      }

      &:target {
        display: flex;
        position: fixed;
        background-color: var(--color-secondary);
        right: 0;
        top: 0;
        height: 100vh;
        width: 50%;
        max-width: 20rem;

        ul {
          flex-direction: column;
        }
      }
    }
  }

  header:has(#nav-open:target) {
    :global(.hamburger-menu) {
      display: none;
    }
    :global(.close-menu) {
      display: flex;
    }
  }
</style>
