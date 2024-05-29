<script lang="ts">
	export let containerStyle: string;
	export let containerTitleStyle: string;

	// Language Stack
	let langStack = new Map([
		['C', 'C'],
		['C++', 'CPP'],
		['Java', 'Java'],
		['Python', 'Python'],
		['TypeScript', 'TypeScript'],
		['VBA', 'VBA'],
		['Shell', 'Bash'],
		['Bash', 'Bash'],
		['Powershell', 'Powershell'],
		['SQL', 'SQL'],
		['HTML', 'HTML5'],
		['CSS', 'CSS3'],
		['Tailwind CSS', 'Tailwind']
	]);

	langStack.forEach((value, key) => {
		langStack.set(key, `/src/lib/images/about/techstack/lang/${value}.svg`);
	});
</script>

<!-- Container/Languages -->
<div class={containerStyle}>
	<!-- Container Title -->
	<span class={containerTitleStyle}>
		{'> ls ~/Languages/'}
	</span>
	<!-- List of Tools -->
	<div class="grid grid-flow-row grid-cols-1 gap-y-[0.625rem] sm:grid-cols-2 md:grid-cols-3">
		<!-- Items -->
		{#each [...langStack] as [key, value]}
			<div class="flex flex-row justify-start items-center space-x-[0.625rem]">
				<img src={value} alt={key} class="h-[1.875rem] w-[1.875rem]" />
				<span class="text-[1.25rem] text-[#a89984]"> {key} </span>
			</div>
		{/each}
	</div>
</div>
