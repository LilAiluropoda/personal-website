<script lang="ts">
	export let containerStyle: string;
	export let containerTitleStyle: string;

	// Dev Environment
	let DEStack = new Map([
		['Arch Linux', 'Arch'],
		['Git', 'Git'],
		['Vim', 'Vim'],
		['VS Code', 'VSCode']
	]);
	// Web dev
	let WDStack = new Map([
		['SvelteKit', 'Svelte'],
		['Vite.js', 'Vite'],
		['Flask', 'Flask']
	]);
	// ML
	let MLStack = new Map([
		['PyTorch', 'PyTorch'],
		['SciKit-Learn', 'SKLearn'],
		['Pandas', 'Pandas'],
		['Matplotlib', 'Matplotlib'],
		['Selenium', 'Selenium']
	]);

	DEStack.forEach((value, key) => {
		DEStack.set(key, `/src/lib/images/about/techstack/dev_env/${value}.svg`);
	});

	WDStack.forEach((value, key) => {
		WDStack.set(key, `/src/lib/images/about/techstack/web_dev/${value}.svg`);
	});

	MLStack.forEach((value, key) => {
		MLStack.set(key, `/src/lib/images/about/techstack/machine-learn/${value}.svg`);
	});
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
						<span class="text-[1.25rem] text-[#a89984]"> {key} </span>
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
						<span class="text-[1.25rem] text-[#a89984]"> {key} </span>
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
						<span class="text-[1.25rem] text-[#a89984]"> {key} </span>
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
