<script>
	import '../app.css';
	import Navbar from '$lib/components/layout/Navbar.svelte';
	import Footer from '$lib/components/layout/Footer.svelte';
</script>

<div class="flex flex-col justify-between w-full min-h-[100vh]">
	<Navbar />
	<slot />
	<Footer />
</div>

<style>
	:global(html) {
		background-color: #3c3836;
		background-size: 2.5rem 2.5rem;
		background-image: linear-gradient(to right, rgba(168, 153, 132, 0.2) 0.3px, transparent 0.3px),
			linear-gradient(to bottom, rgba(168, 153, 132, 0.2) 0.3px, transparent 0.3px);
		background-position: -1rem -1rem;
	}
</style>
