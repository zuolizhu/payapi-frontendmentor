<script>
	export let segment;
</script>

<nav class="desktop-nav">
  <ul>
    <li><a aria-current="{segment === 'pricing' ? 'page' : undefined}" href="pricing">pricing</a></li>
    <li><a aria-current="{segment === 'about' ? 'page' : undefined}" href="about">about</a></li>
    <li><a aria-current="{segment === 'contact' ? 'page' : undefined}" href="contact">contact</a></li>
  </ul>
</nav>

<style>
  .desktop-nav {
    display: none;
  }
</style>