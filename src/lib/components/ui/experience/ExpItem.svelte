<script lang="ts">
	import { ContainerStyle } from '$lib/components/ui/common/Styling.svelte';
	import { mapping } from '$lib/components/ui/common/IconMapper.svelte';
	import TechStackItem from '$lib/components/ui/common/TechStackItem.svelte';

	export let exp;
	let titleColor = '#ffffff';

	if (exp.type === 'WRK') {
		titleColor = '#83a598';
	} else if (exp.type === 'EDU') {
		titleColor = '#d3869b';
	} else if (exp.type === 'ECA') {
		titleColor = '#8ec07c';
	}

	const techStack = mapping(exp.tags);
	let titleStyle = `color:${titleColor}`;
	let expand = false;
</script>

<!-- Dropdown -->
<button on:click={() => (expand = !expand)}>
	<div class={ContainerStyle}>
		<div class="flex flex-col items-start">
			<div class="flex flex-row justify-start space-x-[1rem]">
				<!-- Type -->
				<span class="text-[1.75rem] font-bold text-start" style={titleStyle}>{exp.type}</span>
				<!-- Title -->
				<span class="text-[1.75rem] text-start" style={titleStyle}>{exp.title}</span>
			</div>
			<!-- Company Name -->
			<span class="text-[1.5rem] text-[#a89984]">{exp.org}</span>
		</div>
		<!-- Expanded Content -->
		<div class:show={expand} class:hide={!expand} class="grid h-fit">
			<div class="flex flex-col overflow-hidden space-y-[1rem]">
				<!-- Description -->
				<p class="text-[1.25rem] text-[#a89984] text-justify">
					<!-- TODO -->
					{exp.content}
				</p>
				<!-- TechStack -->
				<div class="flex flex-col justify-start items-start space-y-[0.625rem]">
					<div class="grid w-full gap-[0.625rem] sm:grid-cols-2">
						{#each [...techStack] as [key, value]}
							<TechStackItem image={value} name={key} />
						{/each}
					</div>
				</div>
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
