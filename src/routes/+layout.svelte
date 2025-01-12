<script lang="ts">
	import '../app.css';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';
	let { children } = $props();
</script>

<div class="container mx-auto">
	<Header />
	<article class="prose max-w-none px-6 font-serif">
		{@render children()}
	</article>
	<Footer />
</div>
