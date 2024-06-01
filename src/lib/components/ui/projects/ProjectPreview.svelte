<script lang="ts">
	import { mapping } from '$lib/components/ui/common/IconMapper.svelte';
	import TechStackItem from '$lib/components/ui/common/TechStackItem.svelte';

	export let project;

	const techStack = mapping(project.tags);
</script>

<!-- Container/Project Preview-->
<div
	class="flex flex-col py-[1.25rem] px-[1.88rem] space-y-[0.625rem] w-full h-full min-w-fit bg-[#1d2021] rounded-[0.3125rem] border-[2px] border-[#3c3836] opacity-80 hover:border-[#a89984] hover:opacity-100 transition duration-300"
>
	<!-- Project Image -->
	<img
		src={project.previewImage}
		alt={project.projectName}
		class="w-full max-h-[12.125rem] object-cover overflow-hidden rounded-[0.3125rem] border-[1px] border-[#ebdbb2]"
	/>
	<!-- Project Name -->
	<div class="flex flex-col justify-start items-start">
		<span class="text-[1.25rem] text-[#a89984]">Project Name:</span>
		<span class="text-[1.5rem] text-[#b8bb26] font-bold"> {`${project.projectName}`}</span>
	</div>
	<!-- Project Tags -->
	<div class="flex flex-col justify-start items-start space-y-[0.625rem]">
		<span class="text-[1.25rem] text-[#a89984]">Tags:</span>
		<div class="grid w-full gap-[0.625rem] sm:grid-cols-2">
			{#each [...techStack] as [key, value]}
				<TechStackItem image={value} name={key} />
			{/each}
		</div>
	</div>
</div>
