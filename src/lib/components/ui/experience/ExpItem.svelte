<script lang="ts">
	import { ContainerStyle } from '$lib/components/ui/common/Styling.svelte';
	import { mapping } from '$lib/components/ui/common/IconMapper.svelte';
	import TechStackItem from '$lib/components/ui/common/TechStackItem.svelte';

	const techStack = mapping();

	let expand = false;
</script>

<!-- Dropdown -->
<button on:click={() => (expand = !expand)}>
	<div class={ContainerStyle}>
		<div class="flex flex-col items-start">
			<div class="flex flex-row space-x-[1rem]">
				<!-- Type -->
				<span class="text-[1.875rem] text-[#83a598] font-bold">WRK</span>
				<!-- Title -->
				<span class="text-[1.875rem] text-[#83a598]">Data Analyst</span>
			</div>
			<!-- Company Name -->
			<span class="text-[1.5rem] text-[#a89984]">Societe Generale</span>
		</div>
		<!-- Expanded Content -->
		<div class:show={expand} class:hide={!expand} class="grid h-fit">
			<div class="flex flex-col overflow-hidden">
				<!-- Description -->
				<p class="text-[1.25rem] text-[#a89984]">
					<!-- TODO -->
				</p>
				<!-- TechStack -->
			</div>
		</div>
	</div>
</button>

<style>
	.show {
		grid-template-rows: 1fr;
		transition: grid-template-rows 200ms ease-in;
	}

	.hide {
		grid-template-rows: 0fr;
		transition: grid-template-rows 200ms ease-out;
	}
</style>
