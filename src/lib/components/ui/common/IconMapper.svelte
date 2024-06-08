<script context="module" lang="ts">
	export function mapping(lst: string[]) {
		const mapper = new Map([
			// Language
			['C', 'C'],
			['C++', 'CPP'],
			['Java', 'Java'],
			['Python', 'Python'],
			['TypeScript', 'TypeScript'],
			['VBA', 'VBA'],
			['Shell', 'Bash'],
			['Lua', 'Lua'],
			['Powershell', 'Powershell'],
			['SQL', 'SQL'],
			['HTML', 'HTML5'],
			['CSS', 'CSS3'],
			['Tailwind CSS', 'Tailwind'],
			// Dev Env
			['Arch Linux', 'Arch'],
			['Git', 'Git'],
			['Vim', 'Vim'],
			['VS Code', 'VSCode'],
			// Web dev
			['SvelteKit', 'Svelte'],
			['Vite.js', 'Vite'],
			['Flask', 'Flask'],
			['AWS', 'AWS'],
			// ML
			['PyTorch', 'PyTorch'],
			['SciKit-Learn', 'SKLearn'],
			['Pandas', 'Pandas'],
			['Matplotlib', 'Matplotlib'],
			['Selenium', 'Selenium'],
			['LangChain', 'Meme'],
			// Finance
			['Bloomberg Terminal', 'Meme']
		]);

		let res = new Map();
		lst.forEach((x) => {
			res.set(x, `/images/about/techstack/${mapper.get(x)}.svg`);
		});
		return res;
	}
</script>
