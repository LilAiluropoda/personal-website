<script lang="ts">
	export let image;
	export let name;
</script>

<div class="flex flex-row justify-start items-center space-x-[0.625rem]">
	<img src={image} alt={name} class="h-[1.875rem] w-[1.875rem]" />
	<span class="text-[1.25rem] text-[#a89984] text-start"> {name} </span>
</div>
