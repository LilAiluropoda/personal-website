<script lang="ts">
	import PageHeader from '$lib/components/ui/common/PageHeader.svelte';
	import { ContainerStyle, ContainerTitleStyle } from '$lib/components/ui/common/Styling.svelte';
</script>

<div
	class="flex flex-col px-[0.625rem] pb-[5rem] space-y-[0.625rem] w-full min-h-screen z-0 lg:px-[25%]"
>
	<!-- PageHeader -->
	<PageHeader pageName="EXPERIENCE" textColor="#83A598" />
	<!-- Container/CMDHeader -->
	<div class={ContainerStyle}>
		<span class={ContainerTitleStyle}> {'> journalctl -rb'} </span>
	</div>
	<!-- YearHeader -->
	<div class="flex justify-center items-center w-full h-fit space-x-[1rem]">
		<span class="text-[2.25rem] text-[#ebdbb2] font-bold"> {'-'} </span>
		<span class="text-[2.25rem] text-[#ebdbb2] font-bold"> {'2024'} </span>
		<span class="text-[2.25rem] text-[#ebdbb2] font-bold"> {'-'} </span>
	</div>
	<!-- TODO: Implement the list for rendering experience items -->
</div>
