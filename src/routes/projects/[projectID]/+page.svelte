<script lang="ts">
	import PageHeader from '$lib/components/ui/common/PageHeader.svelte';
	import { ContainerStyle, ContainerTitleStyle } from '$lib/components/ui/common/Styling.svelte';
	import { page } from '$app/stores';
	import SvelteMarkdown from 'svelte-markdown';
	import projectList from '$lib/data/projects.json';
	import { mapping } from '$lib/components/ui/common/IconMapper.svelte';
	import TechStackItem from '$lib/components/ui/common/TechStackItem.svelte';

	const projectID = $page.params.projectID;
	const project = projectList.filter((x) => x.projectID == projectID)[0];
	const TechStack = mapping(project.tags);

	const mdFiles = import.meta.glob(`$lib/data/markdown/*.md`, { eager: true, query: '?raw' });
	const description = Object.entries(mdFiles).filter((x) =>
		x[0].includes(project.description)
	)[0][1].default;
</script>

<div
	class="flex flex-col px-[0.625rem] pb-[5rem] space-y-[0.625rem] w-full min-h-screen z-0 lg:px-[25%]"
>
	<!-- Page Header -->
	<PageHeader pageName="PROJECTS" textColor="#b8bb26" />
	<!-- Container -->
	<div class={ContainerStyle}>
		<!-- CMD Header-->
		<span class={ContainerTitleStyle}> {`> cat ~/projects/${projectID}.md`} </span>
		<!-- project Image -->
		<img
			src={project.previewImage}
			alt={project.projectName}
			class="w-full max-h-[12.125rem] object-cover overflow-hidden rounded-[0.3125rem] border-[1px] border-[#ebdbb2]"
		/>
		<!-- project Name -->
		<div class="flex flex-col justify-start items-start">
			<span class="text-[1.25rem] text-[#a89984]">Project Name:</span>
			<span class="text-[1.5rem] text-[#b8bb26] font-bold"> {`${project.projectName}`}</span>
		</div>
		<div class="flex flex-col justify-start items-start space-y-[0.625rem]">
			<span class="text-[1.25rem] text-[#a89984]">Techstack:</span>
			<div id="list" class="grid w-full gap-[0.625rem]">
				{#each [...TechStack] as [key, value]}
					<TechStackItem image={value} name={key} />
				{/each}
			</div>
		</div>
		<div class="flex flex-col justify-start items-start">
			<span class="text-[1.25rem] text-[#a89984]">Project Description:</span>
			<SvelteMarkdown source={description} />
		</div>
	</div>
</div>

<style lang="css">
	#list {
		grid-template-columns: repeat(auto-fill, minmax(10rem, 1fr));
	}
</style>
