<script lang="ts">
	import { mapping } from '$lib/components/ui/common/IconMapper.svelte';
	import TechStackItem from '$lib/components/ui/common/TechStackItem.svelte';

	export let containerStyle: string;
	export let containerTitleStyle: string;

	const DEStack = mapping(['Arch Linux', 'Git', 'Vim', 'VS Code']);
	const WDStack = mapping(['SvelteKit', 'Vite.js', 'Flask']);
	const MLStack = mapping(['PyTorch', 'SciKit-Learn', 'Pandas', 'Matplotlib', 'Selenium']);
</script>

<div class={containerStyle}>
	<!-- Container Title -->
	<span class={containerTitleStyle}>
		{'> tree -d ~/Tools/'}
	</span>
	<!-- Tree -->
	<span class="text-[1.25rem] text-[#8ec07c] font-bold pb-[-3rem]"> {'~/Tools/'} </span>
	<ul class="pb-[2rem]">
		<li>
			<!-- Development Environment -->
			<span class="text-[1.25rem] text-[#8ec07c] font-bold">
				{'Development Environment'}
			</span>
			<ul>
				{#each [...DEStack] as [key, value]}
					<li class="flex flex-row justify-start items-center space-x-[0.625rem]">
						<img src={value} alt={key} class="h-[1.875rem] w-[1.875rem]" />
						<span class="text-[1.25rem] text-[#a89984] text-start"> {key} </span>
					</li>
				{/each}
			</ul>
		</li>
		<li>
			<!-- Web Development -->
			<span class="text-[1.25rem] text-[#8ec07c] font-bold"> {'Web Development'} </span>
			<ul>
				{#each [...WDStack] as [key, value]}
					<li class="flex flex-row justify-start items-center space-x-[0.625rem]">
						<img src={value} alt={key} class="h-[1.875rem] w-[1.875rem]" />
						<span class="text-[1.25rem] text-[#a89984] text-start"> {key} </span>
					</li>
				{/each}
			</ul>
		</li>
		<li>
			<!-- Machine Learning -->
			<span class="text-[1.25rem] text-[#8ec07c] font-bold"> {'Machine Learning'} </span>
			<ul>
				{#each [...MLStack] as [key, value]}
					<li class="flex flex-row justify-start items-center space-x-[0.625rem]">
						<img src={value} alt={key} class="h-[1.875rem] w-[1.875rem]" />
						<span class="text-[1.25rem] text-[#a89984] text-start"> {key} </span>
					</li>
				{/each}
			</ul>
		</li>
	</ul>
</div>

<style>
	li {
		margin-left: 3rem;
		border-left: 1.8px solid #504945;
		padding-left: 3rem;
		padding-top: 0.625rem;
		padding-bottom: 0.625rem;
	}
</style>
