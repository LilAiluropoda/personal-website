<script lang="ts">
	let menuOpen = false;
</script>

<!-- NavBar -->
<nav class="sticky top-0 flex flex-col justify-center items-center w-full p-[0.625rem]">
	<div
		class="flex flex-row justify-between items-center z-20 w-full px-[1.25rem] py-[0.625rem] rounded-[0.3125rem] bg-[#282828]"
	>
		<!-- UserName -->
		<a href="/" on:click={() => (menuOpen = false)}>
			<div class="flex flex-row">
				<span class="text-[1.7rem] sm:text-[2.25rem] text-[#fe8019]"> Lil </span>
				<span class="text-[1.7rem] sm:text-[2.25rem] text-[#ebdbb2]"> Ailuropoda </span>
			</div>
		</a>
		<!-- BurgerMenu Button -->
		<button id="menuButton" type="button" on:click={() => (menuOpen = !menuOpen)}>
			<div class="relative flex justify-center items-center">
				<svg
					width="50"
					height="50"
					viewBox="0 0 50 50"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M10.4167 25H39.5833M10.4167 14.5833H39.5833M10.4167 35.4167H39.5833"
						stroke="#A89984"
						stroke-width="4.16667"
						stroke-linecap="round"
					/>
				</svg>
			</div>
		</button>
	</div>
	<!-- Menu -->
	<div
		id="megaMenu"
		class:show={menuOpen === true}
		class:hide={menuOpen === false}
		class="absolute z-10 top-[5.5rem] w-full p-[0.625rem]"
		role="menu"
	>
		<div
			class="flex flex-col p-[1.25rem] space-y-[0.625rem] rounded-[0.3125rem] bg-[#504945] border-[1.5px] border-[#928374]"
		>
			<!-- MenuItem/AboutMe -->
			<a href="/about/" on:click={() => (menuOpen = !menuOpen)}>
				<div class="group flex flex-row p-[0.625rem] space-x-[0.625rem]">
					<span class="text-[1.3125rem] sm:text-[1.75rem] text-[#a89984]"> >> </span>
					<span class="text-[1.5rem] sm:text-[2rem] text-[#ebdbb2] group-hover:text-[#8ec07c]">
						About Me
					</span>
				</div>
			</a>
			<a href="/projects/" on:click={() => (menuOpen = !menuOpen)}>
				<div class="group flex flex-row p-[0.625rem] space-x-[0.625rem]">
					<span class="text-[1.3125rem] sm:text-[1.75rem] text-[#a89984]"> >> </span>
					<span class="text-[1.5] sm:text-[2rem] text-[#ebdbb2] group-hover:text-[#b8bb26]">
						Projects
					</span>
				</div>
			</a>
			<a href="/experience/" on:click={() => (menuOpen = !menuOpen)}>
				<div class="group flex flex-row p-[0.625rem] space-x-[0.625rem]">
					<span class="text-[1.3125rem] sm:text-[1.75rem] text-[#a89984]"> >> </span>
					<span class="text-[1.3125rem] sm:text-[2rem] text-[#ebdbb2] group-hover:text-[#83a598]">
						Experience
					</span>
				</div>
			</a>
		</div>
	</div>
</nav>

<style>
	.show {
		visibility: visible;
		animation: slidein 0.5s 1;
		transition: visibility 0.5s;
	}

	.hide {
		visibility: hidden;
		animation: slideout 0.5s 1;
		transition-delay: 0.5s;
		transition: visibility 0.5s;
	}

	@keyframes slidein {
		from {
			transform: translateX(100%);
		}

		to {
			transform: translateX(0%);
		}
	}

	@keyframes slideout {
		from {
			transform: translateX(0%);
		}

		to {
			transform: translateX(100%);
		}
	}
</style>
