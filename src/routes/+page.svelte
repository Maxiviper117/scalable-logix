<script lang="ts">
	import Footer from '$lib/components/Footer.svelte';
	import ButtonLink from '$lib/components/ButtonLink.svelte';
	import { onMount } from 'svelte';

	// Convert skills array into object array with IDs
	const skills = [
		{ id: 1, name: 'JavaScript' },
		{ id: 2, name: 'TypeScript' },
		{ id: 3, name: 'Svelte' },
		{ id: 4, name: 'Sveltekit' },
		{ id: 5, name: 'Node.js' },
		{ id: 6, name: 'Tailwind CSS' },
		{ id: 7, name: 'HTML' },
		{ id: 8, name: 'CSS' },
		{ id: 9, name: 'PostgreSQL' },
		{ id: 10, name: 'Drizzle ORM' },
		{ id: 11, name: 'Prisma ORM' }
	];

	// Track active skill ID with proper typing
	let activeSkillId = $state<number | null>(null);

	onMount(() => {
		const animateSkills = () => {
			// Get random skill ID (different from current active ID)
			let randomId: number;
			do {
				randomId = skills[Math.floor(Math.random() * skills.length)].id;
			} while (randomId === activeSkillId && skills.length > 1);

			// Set new active ID
			activeSkillId = randomId;

			// Set next animation after random delay (between 1 and 3 seconds)
			setTimeout(animateSkills, 2000);
		};

		// Start the animation cycle
		animateSkills();
	});
</script>

<section class="flex min-h-screen items-center px-4 py-12 text-gray-100">
	<div class="container mx-auto max-w-5xl">
		<div class="flex flex-col gap-12">
			<!-- Hero section -->
			<div class="space-y-8 text-center">
				<h1
					class="mb-6 bg-gradient-to-r from-indigo-500 to-purple-600 bg-clip-text text-[clamp(3rem,9vw,120px)] font-bold text-transparent"
				>
					Scalable Logix
				</h1>

				<h2 class="text-5xl">Hi, I'm David</h2>

				<p class="mx-auto mb-8 max-w-3xl text-xl text-gray-300 md:text-2xl">
					I'm a freelance developer specializing in creating beautiful, responsive websites with
					modern technologies that help businesses achieve their goals.
				</p>
				<div class="mt-8">
					<ButtonLink href="/#/contact" text="Get in touch" />
				</div>
			</div>

			<!-- Services section -->
			<div class="bg-card-bg/50 rounded-xl p-8 shadow-lg">
				<h2 class="mb-6 text-center text-2xl font-bold text-indigo-400 md:text-3xl">Services</h2>
				<div class="grid gap-6 md:grid-cols-2">
					<div class="bg-card-bg hover:bg-card-hover rounded-lg p-6 transition-all">
						<h3 class="mb-2 text-xl font-semibold text-indigo-300">Shopify Development</h3>
						<p class="text-gray-400">
							Complete setup and customization for your online store with performance and conversion
							in mind.
						</p>
					</div>
					<div class="bg-card-bg hover:bg-card-hover rounded-lg p-6 transition-all">
						<h3 class="mb-2 text-xl font-semibold text-indigo-300">Website Creation</h3>
						<p class="text-gray-400">
							Custom web solutions designed to meet your business needs and provide exceptional user
							experience.
						</p>
					</div>
					<div class="bg-card-bg hover:bg-card-hover rounded-lg p-6 transition-all">
						<h3 class="mb-2 text-xl font-semibold text-indigo-300">Form Implementation</h3>
						<p class="text-gray-400">
							Functional and user-friendly forms that enhance data collection while maintaining a
							seamless experience.
						</p>
					</div>
					<div class="bg-card-bg hover:bg-card-hover rounded-lg p-6 transition-all">
						<h3 class="mb-2 text-xl font-semibold text-indigo-300">Digital Solutions</h3>
						<p class="text-gray-400">
							A wide range of digital services designed to optimize your online presence and
							operations.
						</p>
					</div>
				</div>
			</div>

			<!-- Skills/Technologies section -->
			<div class="bg-card-bg/50 rounded-xl p-8 shadow-lg">
				<h2 class="mb-6 text-center text-2xl font-bold text-indigo-400 md:text-3xl">
					Technologies
				</h2>
				<div class="grid gap-4 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4">
					{#each skills as skill (skill.id)}
						<div
							class={[
								'bg-card-bg flex items-center justify-center rounded-lg p-4 transition-all hover:bg-card-hover',
								skill.id === activeSkillId ? 'bg-card-hover' : ''
							]}
						>
							<span class="text-xl font-semibold text-indigo-300">{skill.name}</span>
						</div>
					{/each}
				</div>
			</div>

			<!-- CTA section -->
			<div id="contact" class="bg-card-bg/50 rounded-xl p-8 text-center">
				<h2 class="text-text-light mb-4 text-2xl font-bold md:text-3xl">
					Need help with your project?
				</h2>
				<p class="text-text-light/80 mb-6 text-xl">Let's turn your vision into reality.</p>
				<ButtonLink href="/#/contact" text="Let's Talk" />
			</div>

			<!-- Footer -->
			<Footer />
		</div>
	</div>
</section>

