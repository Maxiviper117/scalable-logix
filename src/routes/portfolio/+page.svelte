<script lang="ts">
	import ButtonLink from '$lib/components/ButtonLink.svelte';

	// Portfolio page
	import type { PageData } from './$types';

	let { data }: { data: PageData } = $props();

	// Portfolio data
	const portfolioData = [
		{
			title: 'Bluntbox.co.za',
			description: 'Description of project 1',
			image: 'https://picsum.photos/seed/picsum/800/500',
			link: 'https://bluntbox.co.za'
		},
		{
			title: 'Project 2',
			description: 'Description of project 2',
			image: 'https://picsum.photos/seed/meow/800/500',
			link: '/project-2'
		}
	];
</script>

{#snippet portfolioCard(title: string, description: string, image: string, link: string)}
	<div class="bg-card-bg hover:bg-card-hover flex flex-col space-y-4 rounded-lg p-6 transition-all">
		<h3 class="mb-2 text-xl font-semibold text-indigo-300">{title}</h3>
		<p class="text-gray-400">{description}</p>
		<div class="relative mt-4 h-[400px] w-full">
			<img
				src={image}
				alt={title}
				class="absolute inset-0 h-full w-full rounded-lg object-cover object-center"
			/>
		</div>
		<ButtonLink href={link} text="View Project" class="w-fit" />
	</div>
{/snippet}

<section class="flex items-center px-4 py-6 text-gray-100">
	<div class="container mx-auto">
		<h1 class="text-center text-[clamp(2rem,5vw,3rem)]">Portfolio Projects</h1>
	</div>
</section>
<section class="flex items-center px-4 py-12 text-gray-100">
	<div class="container mx-auto max-w-5xl">
		<div class="grid grid-cols-2 gap-4">
			{#each portfolioData as project}
				{@render portfolioCard(project.title, project.description, project.image, project.link)}
			{/each}
		</div>
	</div>
</section>
