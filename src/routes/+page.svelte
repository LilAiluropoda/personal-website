<script lang="ts">
	import Signature from '$lib/components/ui/home/Signature.svelte';
</script>

<!-- Body -->
<div class="flex flex-col justify-center items-center w-full">
	<Signature />
	<span class="text-[1.75rem] text-[#ebdbb2]"> Personal Website </span>
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
