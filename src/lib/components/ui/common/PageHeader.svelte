<script lang="ts">
	export let pageName: string;
	export let textColor: string;
</script>

<div class="flex justify-center items-center w-full h-fit space-x-[1rem]">
	<span class="text-[2.5rem] text-[#ebdbb2]"> {'{'} </span>
	<span class="text-[2.5rem] font-bold" style="color:{textColor};"> {pageName} </span>
	<span class="text-[2.5rem] text-[#ebdbb2]"> {'}'} </span>
</div>
