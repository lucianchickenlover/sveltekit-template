<script lang="ts">
	import { Clipboard, ClipboardCheck, Github, Twitter } from 'lucide-svelte';

	const packageManagers = { bun: 'bunx', pnpm: 'pnpx', npm: 'npx', yarn: 'yarn dlx' };

	let isCopied = false;
	let showDropdown = false;

	const copyToClipboard = (pm: keyof typeof packageManagers) => {
		showDropdown = false;
		isCopied = true;

		const text = `${packageManagers[pm]} degit rajput-hemant/sveltekit-template <project-name>`;

		try {
			navigator.clipboard.writeText(text);
			isCopied = true;
		} catch (err) {
			console.error('Failed to copy: ', err);
		}
	};
</script>

<svelte:head>
	<title>SvelteKit Starter Template</title>
	<meta
		name="description"
		content="A starter template for SvelteKit w/ TypeScript, TailwindCSS pre-configured with ESLint, Prettier and Husky git hooks."
	/>
</svelte:head>

<main class="layout h-screen w-full bg-black py-12 md:py-24 lg:py-32 xl:py-48">
	<section class="container px-4 md:px-6">
		

		<div class="grid items-center gap-6">
			<div class="flex flex-col justify-center space-y-4 text-center">
				<div class="mb-6 space-y-2">
					<h1
						class="bg-gradient-to-r from-white to-gray-500 bg-clip-text text-3xl font-bold tracking-tighter text-transparent sm:text-5xl xl:text-6xl/none"
					>
						yoursource
					</h1>

					
				</div>

				
			</div>
		</div>
	</section>

	
</main>

<style>
	/* https://github.com/jvidalv/nextal/blob/main/src/components/organisms/layout/layout.module.css */

	.layout {
		background-image: radial-gradient(hsla(0, 0%, 84%, 0.25) 1px, transparent 0),
			radial-gradient(hsla(0, 0%, 65%, 0.2) 1px, transparent 0);
		background-size: 50px 50px;
		background-position:
			0 0,
			25px 25px;
		-webkit-animation: slide 2s linear infinite;
		animation: slide 4s linear infinite;
	}

	@keyframes slide {
		100% {
			background-position:
				50px 0,
				125px 25px;
		}
	}

	::selection {
		color: hsl(0, 0%, 17%);
		background-color: hsl(0, 0%, 100%);
	}
</style>
