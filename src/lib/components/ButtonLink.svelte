<script lang="ts">
	import type { ClassValue } from 'svelte/elements';

	let props: {
		href: string;
		text?: string;
		class?: ClassValue;
		children?: () => any;
	} = $props();
</script>

<a
	href={props.href}
	class={[
		'text-text-light hover:shadow-button-hover-shadow inline-block rounded-lg bg-gradient-to-r from-purple-600 to-indigo-500 px-8 py-3 font-bold uppercase shadow-lg transition-all duration-300 hover:scale-105 hover:bg-indigo-700 active:scale-95',
		props.class
	]}
>
	{props.text}
	{@render props.children?.()}
</a>
