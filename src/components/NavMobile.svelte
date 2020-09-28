<script>
  import { fly } from 'svelte/transition';
  import { acitve } from './stores.js';
  
  let active_status;
  function updateActive() {
    acitve.update((ac) => ac = !ac);
  }
  const unsubscribe = acitve.subscribe(value => {
		active_status = value;
  });
  
</script>

{#if active_status}
<nav on:click={updateActive} transition:fly="{{ x: 200, duration: 500 }}" class="mobile-nav">
  <div class="divider"></div>
  <ul class="mobile-nav-menu">
    <li class="mobile-nav-menu__item"><a class="t-mobile-nav" href="pricing">Pricing</a></li>
    <li class="mobile-nav-menu__item"><a class="t-mobile-nav" href="about">About</a></li>
    <li class="mobile-nav-menu__item"><a class="t-mobile-nav" href="contact">Contact</a></li>
  </ul>
  <a class="button button--cta" href="/">Schedule a Demo</a>
</nav>
{/if}

<style>
  .t-mobile-nav {
    opacity: .70;
    font-size: 2rem;
    line-height: 2.4rem;
    color: var(--color-water-white);
    font-weight: var(--weight-bold);
    font-family: var(--font-family-sans);
  }

  .mobile-nav {
    top: 0;
    right: 0;
    width: 80%;
    height: 100%;
    position: fixed;
    padding: 9.5rem 2.4rem 0;
    background-color: var(--color-mirage-blue);
  }
  @media (min-width: 768px) {
    .mobile-nav {
      display: none;
    }
  }

  .divider {
    opacity: .15;
    height: .1rem;
    background-color: var(--color-water-white);
  }

  .mobile-nav-menu {
    text-align: center;
    margin-top: 4.3rem;
  }

  .mobile-nav-menu__item {
    margin-bottom: 3.2rem;
  }
</style>