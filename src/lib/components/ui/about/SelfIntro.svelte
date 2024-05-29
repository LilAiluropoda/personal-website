<script lang="ts">
	import Propic from '$lib/images/about/propic.jpeg';
	export let containerStyle: string;
	export let containerTitleStyle: string;
</script>

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
