<script>
import { onMount } from 'svelte';

let preloader;

onMount(() => {
  const fadeEffect = setInterval(() => {
    if (!preloader.style.opacity) {
      preloader.style.opacity = 1;
    }
    if (preloader.style.opacity > 0) {
      preloader.style.opacity -= 0.1;
    } else {
      clearInterval(fadeEffect);
      preloader.style.display = 'none';
    }
  }, 100);
  
  window.addEventListener('load', () => fadeEffect);
});

</script>

<div bind:this={preloader} class="preloader">
  <svg width="200" height="200" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="xMidYMid" class="lds-ripple" style="background:0 0"><circle cx="50" cy="50" r="4.719" fill="none" stroke="#ba4270" stroke-width="2"><animate attributeName="r" calcMode="spline" values="0;40" keyTimes="0;1" dur="3" keySplines="0 0.2 0.8 1" begin="-1.5s" repeatCount="indefinite"/><animate attributeName="opacity" calcMode="spline" values="1;0" keyTimes="0;1" dur="3" keySplines="0.2 0 0.8 1" begin="-1.5s" repeatCount="indefinite"/></circle><circle cx="50" cy="50" r="27.591" fill="none" stroke="#da6d97" stroke-width="2"><animate attributeName="r" calcMode="spline" values="0;40" keyTimes="0;1" dur="3" keySplines="0 0.2 0.8 1" begin="0s" repeatCount="indefinite"/><animate attributeName="opacity" calcMode="spline" values="1;0" keyTimes="0;1" dur="3" keySplines="0.2 0 0.8 1" begin="0s" repeatCount="indefinite"/></circle></svg>
</div>

<style>
  .preloader {
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    z-index: 10;
    display: flex;
    position: fixed;
    align-items: center;
    justify-content: center;
    transition: opacity 0.3s linear;
    background: var(--color-bg-blue);
  }
</style>