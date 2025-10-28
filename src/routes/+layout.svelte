<script lang="ts">
  import Navigation from '$lib/components/Navigation.svelte';
  export const prerender = true;
  import favicon from '/favicon.ico';

  let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<style>
  header {
    background-color: var(--primary-green);
    color: var(--white);
    padding: 1.5rem;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  }

  .logo {
    max-width: 450px;
  }

  .logo:hover {
    transform: scale(1.05);
  }

  footer {
    background-color: var(--dark-grey);
    color: var(--white);
    text-align: center;
    padding: 1.5rem;
    margin-top: 2rem;
    font-family: 'Roboto', sans-serif;
  }

  @media (max-width: 768px) {
    .logo {
      max-width: 200px;
    }
  }
</style>

<header>
  <img src="/header.png" alt="Saneco66 Logo" class="logo" />
</header>

<Navigation />

{@render children?.()}

<!-- <slot /> -->

<footer>
  <p>&copy; 2025 Saneco66. Все права защищены.</p>
</footer>
