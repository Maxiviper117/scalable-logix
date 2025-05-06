<script lang="ts">
	import '../app.css';
	import Nav from '$lib/components/Nav.svelte';
	import { onNavigate } from '$app/navigation';

	export const prerender = true;

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

{@render children()}
