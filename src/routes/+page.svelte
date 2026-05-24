<script lang="ts">
	import Signature from '$lib/components/ui/home/Signature.svelte';
</script>

<svelte:head>
	<title>Steve's Homepage</title>
	<meta name="google-site-verification" content="YOUR_GOOGLE_VERIFICATION_CODE" />
	<meta
		name="description"
		content="Steve Cheng's personal website — Computer Science student at CUHK, passionate about technology, food, music, and new knowledge."
	/>
	<meta
		name="keywords"
		content="Steve Cheng, personal website, computer science, CUHK, portfolio, developer"
	/>
	<meta property="og:title" content="Steve's Homepage" />
	<meta
		property="og:description"
		content="Steve Cheng's personal website — Computer Science student at CUHK, passionate about technology, food, music, and new knowledge."
	/>
	<meta property="og:type" content="website" />
	<meta property="og:image" content="/images/icon_light.png" />
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:title" content="Steve's Homepage" />
	<meta
		name="twitter:description"
		content="Steve Cheng's personal website — Computer Science student at CUHK, passionate about technology, food, music, and new knowledge."
	/>
</svelte:head>

<!-- Body -->
<div class="flex flex-col justify-center items-center w-full min-h-[90vh] space-y-[0.625rem]">
	<Signature />
	<span class="text-[1.75rem] text-[#ebdbb2]"> Personal Website </span>
</div>

<style>
</style>
