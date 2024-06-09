<script lang="ts">
	import PageHeader from '$lib/components/ui/common/PageHeader.svelte';
	import { ContainerStyle, ContainerTitleStyle } from '$lib/components/ui/common/Styling.svelte';
	import YearHeader from '$lib/components/ui/experience/YearHeader.svelte';
	import ExpItem from '$lib/components/ui/experience/ExpItem.svelte';
	import expList from '$lib/data/experience.json';

	let expByYear = new Map();
	// Group by year
	expList.forEach((item) => {
		if (expByYear.has(item.year) === false) {
			expByYear.set(item.year, [item]);
			return;
		}
		expByYear.get(item.year).push(item);
	});
</script>

<svelte:head>
	<title>My Experience</title>
</svelte:head>

<div
	class="flex flex-col px-[0.625rem] pb-[5rem] space-y-[0.625rem] w-full min-h-screen z-0 lg:px-[25%]"
>
	<!-- PageHeader -->
	<PageHeader pageName="EXPERIENCE" textColor="#83A598" />
	<!-- Container/CMDHeader -->
	<div class={ContainerStyle}>
		<span class={ContainerTitleStyle}> {'> journalctl -rb'} </span>
	</div>
	<!-- TODO: Implement the list for rendering experience items -->
	<div class="flex flex-col">
		{#each [...expByYear] as [year, list]}
			<!-- YearHeader -->
			<YearHeader {year} />
			{#each list as exp}
				<ExpItem {exp} />
			{/each}
		{/each}
	</div>
</div>
