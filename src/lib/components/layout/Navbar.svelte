<script lang="ts">
	import { SignIn, SignOut } from '@auth/sveltekit/components';
	import { page } from '$app/stores';

	let menuOpen = false;

	$: session = $page.data.session;
</script>

<!-- NavBar -->
<nav class="sticky top-0 flex flex-col justify-center items-center w-full p-[0.625rem]">
	<div
		class="flex flex-row justify-between items-center z-20 w-full px-[1.25rem] py-[0.625rem] rounded-[0.3125rem] bg-[#282828]"
	>
		<!-- UserName -->
		<a href="/" on:click={() => (menuOpen = false)}>
			<div class="flex flex-row">
				<span class="text-[2.25rem] text-[#fe8019]"> Lil </span>
				<span class="text-[2.25rem] text-[#ebdbb2]"> Ailuropoda </span>
			</div>
		</a>
		<!-- Right Controls -->
		<div class="flex flex-row items-center space-x-[0.75rem]">
			<!-- SSO Auth -->
			{#if session?.user}
				<!-- User Avatar + Sign Out -->
				<div class="flex flex-row items-center space-x-[0.5rem]">
					{#if session.user.image}
						<img
							src={session.user.image}
							alt={session.user.name ?? 'User avatar'}
							class="w-[2.5rem] h-[2.5rem] rounded-full border-[2px] border-[#a89984]"
							referrerpolicy="no-referrer"
						/>
					{/if}
					<span class="hidden sm:block text-[1rem] text-[#ebdbb2]"
						>{session.user.name ?? session.user.email}</span
					>
					<SignOut>
						<div
							slot="submitButton"
							class="flex justify-center items-center px-[0.75rem] py-[0.375rem] rounded-[0.3125rem] bg-[#504945] border-[1.5px] border-[#928374] hover:border-[#fb4934] transition duration-300"
						>
							<span class="text-[0.875rem] text-[#a89984] hover:text-[#fb4934]">Sign out</span>
						</div>
					</SignOut>
				</div>
			{:else}
				<!-- Sign In with GitHub -->
				<SignIn provider="github">
					<div
						slot="submitButton"
						class="flex flex-row items-center space-x-[0.5rem] px-[0.75rem] py-[0.375rem] rounded-[0.3125rem] bg-[#504945] border-[1.5px] border-[#928374] hover:border-[#fe8019] transition duration-300"
					>
						<svg
							width="20"
							height="20"
							viewBox="0 0 40 40"
							fill="none"
							xmlns="http://www.w3.org/2000/svg"
						>
							<g clip-path="url(#clip0_sso_github)">
								<path
									fill-rule="evenodd"
									clip-rule="evenodd"
									d="M20.0165 0C8.94791 0 0 9.01388 0 20.1653C0 29.0792 5.73324 36.6246 13.6868 39.2952C14.6812 39.4959 15.0454 38.8613 15.0454 38.3274C15.0454 37.8599 15.0126 36.2575 15.0126 34.5879C9.4445 35.79 8.28498 32.1841 8.28498 32.1841C7.39015 29.847 6.06429 29.2463 6.06429 29.2463C4.24185 28.011 6.19704 28.011 6.19704 28.011C8.21861 28.1446 9.27938 30.081 9.27938 30.081C11.0686 33.1522 13.9518 32.2844 15.1118 31.7502C15.2773 30.4481 15.8079 29.5467 16.3713 29.046C11.9303 28.5785 7.25781 26.8425 7.25781 19.0967C7.25781 16.8932 8.05267 15.0905 9.31216 13.6884C9.11344 13.1877 8.41733 11.1174 9.51128 8.34644C9.51128 8.34644 11.2014 7.81217 15.0122 10.4164C16.6438 9.97495 18.3263 9.7504 20.0165 9.74851C21.7067 9.74851 23.4295 9.98246 25.0205 10.4164C28.8317 7.81217 30.5218 8.34644 30.5218 8.34644C31.6158 11.1174 30.9192 13.1877 30.7205 13.6884C32.0132 15.0905 32.7753 16.8932 32.7753 19.0967C32.7753 26.8425 28.1028 28.5449 23.6287 29.046C24.358 29.6802 24.9873 30.882 24.9873 32.7851C24.9873 35.4893 24.9545 37.6596 24.9545 38.327C24.9545 38.8613 25.3192 39.4959 26.3132 39.2956C34.2667 36.6242 39.9999 29.0792 39.9999 20.1653C40.0327 9.01388 31.052 0 20.0165 0Z"
									fill="#A89984"
								/>
							</g>
							<defs>
								<clipPath id="clip0_sso_github">
									<rect width="40" height="40" fill="white" />
								</clipPath>
							</defs>
						</svg>
						<span class="hidden sm:block text-[0.875rem] text-[#a89984]">Sign in</span>
					</div>
				</SignIn>
			{/if}
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
	</div>
	<!-- Menu -->
	<div
		id="megaMenu"
		class:show={menuOpen === true}
		class:hide={menuOpen === false}
		class="absolute z-10 top-[6.25rem] w-full p-[0.625rem]"
		role="menu"
	>
		<div
			class="flex flex-col p-[1.25rem] space-y-[0.625rem] rounded-[0.3125rem] bg-[#504945] border-[1.5px] border-[#928374]"
		>
			<!-- MenuItem/AboutMe -->
			<a href="/about/" on:click={() => (menuOpen = !menuOpen)}>
				<div class="group flex flex-row p-[0.625rem] space-x-[0.625rem]">
					<span class="text-[1.75rem] text-[#a89984]"> >> </span>
					<span class="text-[2rem] text-[#ebdbb2] group-hover:text-[#8ec07c]"> About Me </span>
				</div>
			</a>
			<a href="/projects/" on:click={() => (menuOpen = !menuOpen)}>
				<div class="group flex flex-row p-[0.625rem] space-x-[0.625rem]">
					<span class="text-[1.75rem] text-[#a89984]"> >> </span>
					<span class="text-[2rem] text-[#ebdbb2] group-hover:text-[#b8bb26]"> Projects </span>
				</div>
			</a>
			<a href="/experience/" on:click={() => (menuOpen = !menuOpen)}>
				<div class="group flex flex-row p-[0.625rem] space-x-[0.625rem]">
					<span class="text-[1.75rem] text-[#a89984]"> >> </span>
					<span class="text-[2rem] text-[#ebdbb2] group-hover:text-[#83a598]"> Experience </span>
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
