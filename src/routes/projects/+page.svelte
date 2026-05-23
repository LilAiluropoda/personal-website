<script lang="ts">
	import ProjectPreview from '$lib/components/ui/projects/ProjectPreview.svelte';
	import PageHeader from '$lib/components/ui/common/PageHeader.svelte';
	import projectList from '$lib/data/projects.json';
	import { ContainerStyle, ContainerTitleStyle } from '$lib/components/ui/common/Styling.svelte';
	import { goto } from '$app/navigation';

	//Dynamic Routing
	function route(projectID: string) {
		setTimeout(() => goto(`/projects/${projectID}`), 0);
	}
</script>

<svelte:head
	><title>Projects | Steve Cheng</title>
	<meta
		name="description"
		content="Explore Steve Cheng's projects — from web development and machine learning to trading strategies and Linux customisation."
	/>
	<meta
		name="keywords"
		content="Steve Cheng, projects, portfolio, web development, machine learning, SvelteKit, Python"
	/>
	<meta property="og:title" content="Projects | Steve Cheng" />
	<meta
		property="og:description"
		content="Explore Steve Cheng's projects — from web development and machine learning to trading strategies and Linux customisation."
	/>
	<meta property="og:type" content="website" />
	<meta property="og:image" content="/images/icon_light.png" />
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:title" content="Projects | Steve Cheng" />
	<meta
		name="twitter:description"
		content="Explore Steve Cheng's projects — from web development and machine learning to trading strategies and Linux customisation."
	/>
</svelte:head>

<div
	class="flex flex-col px-[0.625rem] pb-[5rem] space-y-[0.625rem] w-full min-h-screen z-0 lg:px-[25%]"
>
	<!-- Page Header -->
	<PageHeader pageName="PROJECTS" textColor="#b8bb26" />
	<!-- Container/CMDHeader -->
	<div class={ContainerStyle}>
		<span class={ContainerTitleStyle}> {'> dolphin ~/Projects/'} </span>
	</div>
	<!-- Project List-->
	<div id="list" class="grid w-full justify-center place-items-stretch gap-[1rem]">
		{#each projectList as project}
			<button
				class="w-full"
				on:click={() => {
					route(project.projectID);
				}}
			>
				<ProjectPreview {project} />
			</button>
		{/each}
	</div>
</div>

<style lang="css">
	#list {
		grid-template-columns: repeat(auto-fill, minmax(25rem, 1fr));
	}
</style>
