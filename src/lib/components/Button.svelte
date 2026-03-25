<script>
  let {
    type,
    variant = "primary",
    size = "md",
    href,
    as,
    children,
    ...rest
  } = $props();

  const tagName = $derived(as || (href ? "a" : "button"));
</script>

<svelte:element
  this={tagName}
  {href}
  {type}
  class="btn {variant} {size}"
  {...rest}
>
  {@render children?.()}
</svelte:element>

<style>
  .btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    border-radius: 4px;
    transition: all 0.2s ease;
    cursor: pointer;
    text-decoration: none;
    border: 2px solid transparent;
  }

  /* Variants */
  .primary {
    background-color: var(--color-secondary);
    color: rgb(255, 255, 255);
  }

  .primary:hover {
    filter: brightness(1.1);
    transform: translateY(-2px);
  }

  .secondary {
    background-color: var(--color-secondary);
    border-color: var(--color-primary);
    color: var(--color-primary);
  }

  .secondary:hover {
    background-color: var(--color-primary);
    color: var(--color-secondary);
  }

  .ghost {
    background: transparent;
    color: var(--color-primary);
    padding: 0;
  }

  .ghost:hover {
    color: rgb(112, 98, 21);
  }
</style>
