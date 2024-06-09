<script lang="ts">
	import PageHeader from '$lib/components/ui/common/PageHeader.svelte';
	import SelfIntro from '$lib/components/ui/about/SelfIntro.svelte';
	import Lang from '$lib/components/ui/about/Lang.svelte';
	import Tools from '$lib/components/ui/about/Tools.svelte';
	import { ContainerStyle, ContainerTitleStyle } from '$lib/components/ui/common/Styling.svelte';
</script>

<svelte:head>
	<title>About Me</title>
</svelte:head>

<div
	class="flex flex-col px-[0.625rem] pb-[5rem] space-y-[0.625rem] w-full min-h-screen z-0 lg:px-[25%]"
>
	<!-- Page Header -->
	<PageHeader pageName="ABOUT ME" textColor="#8ec07c" />
	<!-- Container/Self-Intro -->
	<SelfIntro containerStyle={ContainerStyle} containerTitleStyle={ContainerTitleStyle} />
	<!-- Container/Languages -->
	<Lang containerStyle={ContainerStyle} containerTitleStyle={ContainerTitleStyle} />
	<!-- Container/Tools -->
	<Tools containerStyle={ContainerStyle} containerTitleStyle={ContainerTitleStyle} />
</div>
