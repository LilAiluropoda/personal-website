<script lang="ts">
	import { mapping } from '$lib/components/ui/common/IconMapper.svelte';
	import TechStackItem from '$lib/components/ui/common/TechStackItem.svelte';

	export let containerStyle: string;
	export let containerTitleStyle: string;

	let langStack = mapping([
		'C',
		'C++',
		'Java',
		'Python',
		'TypeScript',
		'VBA',
		'Shell',
		'Powershell',
		'SQL',
		'HTML',
		'CSS',
		'Tailwind CSS'
	]);
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
			<TechStackItem image={value} name={key} />
		{/each}
	</div>
</div>
