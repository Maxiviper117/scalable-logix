<script lang="ts">
	import '../app.css';
	import Nav from '$lib/components/Nav.svelte';
	import { onNavigate } from '$app/navigation';

	onNavigate((navigation) => {
		if (!document.startViewTransition) return;

		return new Promise((resolve) => {
			document.startViewTransition(async () => {
				resolve();
				await navigation.complete;
			});
		});
	});
	let { children } = $props();
</script>

<Nav />
<main class="bg-background min-h-screen">
	{@render children()}
</main>
