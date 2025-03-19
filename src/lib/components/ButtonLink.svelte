<script lang="ts">
	let props: {
		href: string;
		text: string;
		class?: string;
	} = $props();
</script>

<a
	href={props.href}
	class={[
		'text-text-light  bg-gradient-to-r to-indigo-500 from-purple-600 hover:shadow-button-hover-shadow inline-block rounded-lg px-8 py-3 font-medium shadow-lg transition-all duration-300 hover:bg-indigo-700 active:scale-95 hover:scale-105',
		props.class
	]}
>
	{props.text}
</a>
