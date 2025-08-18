<script>
  import { slide } from 'svelte/transition';
  let isMenuOpen = false;

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
</script>

<style>
  nav {
    background-color: var(--accent-green);
    padding: 0.75rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  }

  .menu-toggle {
    display: none;
    background: none;
    border: none;
    color: var(--white);
    font-size: 1.5rem;
    cursor: pointer;
    padding: 0.5rem;
  }

  ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: center;
    gap: 1rem;
  }

  li {
    display: flex;
    align-items: center;
    background-color: transparent;
  }

  li a {
    color: var(--white);
    text-decoration: none;
    font-family: 'Roboto', sans-serif;
    font-weight: 500;
    font-size: 1rem;
    padding: 0.5rem 1rem;
    border-radius: 4px;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: background-color 0.3s ease, color 0.3s ease;
  }

  li a:hover {
    background-color: var(--hover-green);
    color: var(--hover-light-green);
  }

  .material-icons {
    font-size: 1.2rem;
  }

  @media (max-width: 768px) {
    .menu-toggle {
      display: block;
      position: absolute;
      top: 0.75rem;
      right: 1rem;
    }

    ul {
      display: none;
      flex-direction: column;
      background-color: var(--accent-green);
      position: absolute;
      top: 100%;
      left: 0;
      width: 100%;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    ul.open {
      display: flex;
    }

    li {
      padding: 0.5rem;
      margin: 0;
    }

    li a {
      font-size: 0.9rem;
      padding: 0.75rem;
    }
  }
</style>

<nav>
  <button class="menu-toggle" on:click={toggleMenu}>
    <span class="material-icons">{isMenuOpen ? 'close' : 'menu'}</span>
  </button>
  {#if isMenuOpen}
    <ul class:open={isMenuOpen} transition:slide={{ duration: 300 }}>
      <li><a href="#home"><span class="material-icons">home</span>Главная</a></li>
      <li><a href="#services"><span class="material-icons">build</span>Услуги</a></li>
      <li><a href="#about"><span class="material-icons">info</span>О нас</a></li>
      <li><a href="#discounts"><span class="material-icons">local_offer</span>Скидки</a></li>
      <li><a href="#contact"><span class="material-icons">contact_mail</span>Контакты</a></li>
    </ul>
  {:else}
    <ul>
      <li><a href="#home"><span class="material-icons">home</span>Главная</a></li>
      <li><a href="#services"><span class="material-icons">build</span>Услуги</a></li>
      <li><a href="#about"><span class="material-icons">info</span>О нас</a></li>
      <li><a href="#discounts"><span class="material-icons">local_offer</span>Скидки</a></li>
      <li><a href="#contact"><span class="material-icons">contact_mail</span>Контакты</a></li>
    </ul>
  {/if}
</nav>
