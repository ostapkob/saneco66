
<script>
  import Services from '$lib/components/Services.svelte';
  import About from '$lib/components/About.svelte';
  import Discounts from '$lib/components/Discounts.svelte';
  import Contacts from '$lib/components/Contacts.svelte';
</script>

<style>
  .hero {
    background-color: var(--light-green);
    padding: 3rem 1rem;
    text-align: center;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }

  /* .contact { */
  /*   composes: card from 'styles.css'; */
  /* } */

  @media (max-width: 768px) {
    .hero {
      padding: 2rem 1rem;
    }
  }
</style>

<section class="hero" id="home">
  <h2>Избавим вас от насекомых быстро и безопасно!</h2>
  <p>Компания Saneco66 предоставляет профессиональные услуги по дезинсекции в Екатеринбурге и Свердловской области.</p>
</section>

<Services />
<About />
<Discounts />
<Contacts />

