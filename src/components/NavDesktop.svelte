<script>
	export let segment;
</script>

<nav class="desktop-nav">
  <ul class="desktop-nav-menu">
    <li class="desktop-nav-menu__item"><a class="t-desktop-nav" aria-current="{segment === 'pricing' ? 'page' : undefined}" href="pricing">Pricing</a></li>
    <li class="desktop-nav-menu__item"><a class="t-desktop-nav" aria-current="{segment === 'about' ? 'page' : undefined}" href="about">About</a></li>
    <li class="desktop-nav-menu__item"><a class="t-desktop-nav" aria-current="{segment === 'contact' ? 'page' : undefined}" href="contact">Contact</a></li>
  </ul>
  <a class="button button--cta" href="/">Schedule a Demo</a>
</nav>

<style>
  .desktop-nav {
    display: none;
  }
  @media (min-width: 768px) {
    .desktop-nav {
      width: 100%;
      margin-left: 6.4rem;
      align-items: center;
      display: inline-flex;
    }

    .desktop-nav > .button {
      margin-left: auto;
    }
  }

  .t-desktop-nav {
    opacity: .70;
    font-size: 1.5rem;
    line-height: 1.7rem;
    color: var(--color-juan-blue);
    font-weight: var(--weight-bold);
    font-family: var(--font-family-sans);
  }


  .desktop-nav-menu {
    display: inline-flex;
  }

  .desktop-nav-menu__item:not(:last-of-type) {
    margin-right: 4rem;
  }


</style>