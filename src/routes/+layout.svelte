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
