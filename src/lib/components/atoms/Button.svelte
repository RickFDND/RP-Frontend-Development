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

  /* Sizes */
  .sm {
    padding: var(--space-2) var(--space-4);
    font-size: var(--text-sm);
  }
  .md {
    padding: var(--space-4) var(--space-8);
    font-size: var(--text-base);
  }
  .lg {
    padding: var(--space-6) var(--space-12);
    font-size: var(--text-lg);
  }

  /* Variants */
  .primary {
    background-color: var(--color-accent);
    color: var(--color-secondary);
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
    color: rgb(139, 122, 24);
  }
</style>
