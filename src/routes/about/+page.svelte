<script lang="ts">
	import PageHeader from '$lib/components/ui/common/PageHeader.svelte';
	import SelfIntro from '$lib/components/ui/about/SelfIntro.svelte';
	import Lang from '$lib/components/ui/about/Lang.svelte';
	import Tools from '$lib/components/ui/about/Tools.svelte';
	import { ContainerStyle, ContainerTitleStyle } from '$lib/components/ui/common/Styling.svelte';
</script>

<svelte:head>
	<title>About Me | Steve Cheng</title>
	<meta
		name="description"
		content="Learn about Steve Cheng — a Computer Science student at CUHK passionate about development, food, music, sceneries, and new knowledge."
	/>
	<meta
		name="keywords"
		content="Steve Cheng, about, computer science, CUHK, developer, portfolio"
	/>
	<meta property="og:title" content="About Me | Steve Cheng" />
	<meta
		property="og:description"
		content="Learn about Steve Cheng — a Computer Science student at CUHK passionate about development, food, music, sceneries, and new knowledge."
	/>
	<meta property="og:type" content="website" />
	<meta property="og:image" content="/images/icon_light.png" />
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:title" content="About Me | Steve Cheng" />
	<meta
		name="twitter:description"
		content="Learn about Steve Cheng — a Computer Science student at CUHK passionate about development, food, music, sceneries, and new knowledge."
	/>
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
