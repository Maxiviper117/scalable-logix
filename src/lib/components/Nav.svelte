<script lang="ts">
	let props = $props();
</script>

{#snippet navLink(text: string, href: string)}
	<li>
		<a class="text-text-light hover:text-accent" {href}>{text}</a>
	</li>
{/snippet}

<nav class="bg-background">
	<ul class="flex items-center justify-center gap-10 p-4 text-xl">
			{@render navLink('Home', '/')}
			<!-- {@render navLink('Portfolio', '/#/portfolio')} -->
			{@render navLink('Contact', '/#/contact')}
		</ul>
</nav>
