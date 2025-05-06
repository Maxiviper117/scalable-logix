<script lang="ts">
	import ButtonLink from '$lib/components/ButtonLink.svelte';

	// Portfolio page
	import type { PageData } from './$types';

	let { data }: { data: PageData } = $props();

	// Portfolio data
	const portfolioData = [
		{
			title: 'Bluntbox.co.za',
			description: 'A Cannabis landing page for Bluntbox, a cannabis membership site.',
			image: '/images/Screenshot_bluntbox.co.za.jpeg',
			link: 'https://bluntbox.co.za',
			tech: ['Sveltekit', 'Tailwind CSS', 'Node Mailer', 'TypeScript', 'Zod Validation']
		},
		{
			title: 'Top Rental',
			description:
				'A local car leasing company with a custom-built website and admin panel for self managing vehicle listings easily.',
			image: 'https://picsum.photos/seed/meow/800/500',
			link: '/project-2',
			tech: ['Sveltekit', 'Tailwind CSS', 'Drizzle ORM', 'PostgreSQL', 'Zod Validation','S3 Storage']
		}
	];
</script>

{#snippet portfolioCard(
	title: string,
	description: string,
	image: string,
	link: string,
	tech: string[]
)}
	<div
		class="bg-card-bg hover:bg-card-hover row-span-5 grid grid-rows-subgrid rounded-lg p-6 transition-all group"
	>
		<h3 class="mb-2 text-xl font-semibold text-indigo-300">{title}</h3>
		<p class="text-gray-400">{description}</p>
		<div class="relative mt-4 h-[400px] w-full">
			<img
				src={image}
				alt={title}
				class="absolute inset-0 h-full w-full rounded-lg object-cover object-center"
			/>
		</div>
		<div>
			{#if tech}
				<ul class="mt-2 flex flex-wrap gap-2">
					{#each tech as item}
						<li class="bg-card-hover rounded-full px-3 py-1 text-sm font-semibold text-gray-300 group-hover:bg-background">
							{item}
						</li>
					{/each}
				</ul>
			{/if}
		</div>
		<ButtonLink href={link} class="w-fit">View</ButtonLink>
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
				{@render portfolioCard(
					project.title,
					project.description,
					project.image,
					project.link,
					project.tech
				)}
			{/each}
		</div>
	</div>
</section>
