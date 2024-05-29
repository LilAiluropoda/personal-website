<script lang="ts">
	import Propic from '$lib/images/about/propic.jpeg';
	import PageHeader from '$lib/components/ui/common/PageHeader.svelte';

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

	// Generic Styling
	let containerStyle =
		'flex flex-col py-[1.25rem] px-[1.88rem] space-y-[0.625rem] w-full bg-[#1d2021] rounded-[0.3125rem] border-[2px] border-[#a89984]';
	let containerTitleStyle = 'text-[1.5rem] text-[#ebdbb2]';
</script>

<div class="flex flex-col px-[0.625rem] pb-[5rem] space-y-[0.625rem] w-full min-h-screen z-0">
	<!-- Page Header -->
	<PageHeader pageName="ABOUT ME" textColor="#8ec07c" />

	<!-- Container/Self-Intro -->
	<div class={containerStyle}>
		<!-- Container Title -->
		<span class={containerTitleStyle}>
			{'> cat ~/readme.md'}
		</span>
		<div class="flex flex-col items-center">
			<!-- Image -->
			<div class="flex flex-col justify-center items-center py-[1rem]">
				<img
					src={Propic}
					alt="The Great Gatsby Himself"
					class="backdrop-grayscale object-contain w-[11.875rem] h-[11.875rem] rounded-[0.3125rem]"
				/>
				<!-- Name -->
				<div class="flex justify-center w-full">
					<span class="text-[2rem] text-[#ebdbb2] font-bold"> Steve Cheng </span>
				</div>
			</div>
			<!-- Paragraph -->
			<div class="w-full">
				<!-- Description -->
				<p class="text-[1.25rem] text-[#a89984]">
					Hey there, great to have you on my page! <br /> <br /> I'm
					<span class="text-[#8ec07c]">Steve</span>, a Computer Science student at CUHK who's all
					about that
					<span class="text-[#8ec07c]"> awesome sense of progress</span>. <br /> I get thrilled by
					things like
					<span class="text-[#8ec07c]"> food</span>, <span class="text-[#8ec07c]"> music</span>,
					<span class="text-[#8ec07c]"> sceneries</span>, and
					<span class="text-[#8ec07c]">new knowledge</span>! <br /> <br />
					I use <span class="text-[#1793d1]">Arch</span> btw.
				</p>
			</div>
		</div>
	</div>

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

	<!-- Container/Tools -->
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
