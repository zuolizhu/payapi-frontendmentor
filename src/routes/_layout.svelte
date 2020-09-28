<script>
	import Header from '../components/Header.svelte';
	import Footer from '../components/Footer.svelte';
	import PreLoader from '../components/PreLoader.svelte';
	export let segment;
</script>

<PreLoader/>
<Header {segment}/>
<main>
	<slot></slot>
</main>
<Footer/>