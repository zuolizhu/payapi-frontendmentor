<script>
  import { acitve } from './stores.js';
  function updateActive() {
    acitve.update((ac) => ac = !ac);
  }
</script>

<button
  on:click={updateActive}
  aria-label="mobile burger"
  title="mobile burger" 
  class="button button--burger">
  <span class="sr-only">Burger button</span>
  <svg class="button--burger__icon {!$acitve ? 'active': ''}" width="28" height="17" xmlns="http://www.w3.org/2000/svg"><g fill="#36536B" fill-rule="evenodd"><path d="M0 0h28v3H0zM0 7h28v3H0zM0 14h28v3H0z"/></g></svg>
  <svg class="button--burger__icon {$acitve ? 'active': ''}" width="22" height="23" xmlns="http://www.w3.org/2000/svg"><path d="M19.839.54L21.96 2.66 13.12 11.5l8.84 8.839-2.121 2.121-8.84-8.84-8.838 8.84L.04 20.34l8.838-8.84L.04 2.662 2.16.54 11 9.378 19.839.54z" fill="#FBFCFE" fill-rule="evenodd"/></svg>
</button>

<style>
.button--burger {
  z-index: 1;
  cursor: pointer;
  position: relative;
  display: inline-block;
}
@media (min-width: 768px) {
  .button--burger {
    display: none;
  }
}

.button--burger__icon {
  display: none;
}
.button--burger__icon.active {
  display: inline-flex;
}
</style>