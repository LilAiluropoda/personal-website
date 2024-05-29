<script lang="ts">
	import PageHeader from '$lib/components/ui/common/PageHeader.svelte';
	import SelfIntro from '$lib/components/ui/about/SelfIntro.svelte';
	import Lang from '$lib/components/ui/about/Lang.svelte';
	import Tools from '$lib/components/ui/about/Tools.svelte';

	// Generic Styling
	let containerStyle =
		'flex flex-col py-[1.25rem] px-[1.88rem] space-y-[0.625rem] w-full bg-[#1d2021] rounded-[0.3125rem] border-[2px] border-[#3c3836] opacity-80 hover:border-[#a89984] hover:opacity-100';
	let containerTitleStyle = 'text-[1.5rem] text-[#ebdbb2]';
</script>

<div class="flex flex-col px-[0.625rem] pb-[5rem] space-y-[0.625rem] w-full min-h-screen z-0">
	<!-- Page Header -->
	<PageHeader pageName="ABOUT ME" textColor="#8ec07c" />
	<!-- Container/Self-Intro -->
	<SelfIntro {containerStyle} {containerTitleStyle} />
	<!-- Container/Languages -->
	<Lang {containerStyle} {containerTitleStyle} />
	<!-- Container/Tools -->
	<Tools {containerStyle} {containerTitleStyle} />
</div>
