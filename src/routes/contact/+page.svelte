<script lang="ts">
	import type { PageData } from './$types';

	let { data }: { data: PageData } = $props();

	let isLoading = $state(true);
</script>

<section>
	{#if isLoading}
		<p class="text-center text-2xl font-bold text-gray-500 dark:text-gray-400">
			Loading... <span class="animate-pulse">⏳</span>
		</p>
	{/if}

	<!-- svelte-ignore a11y_missing_attribute -->
	<iframe
		aria-label="Scalable Logix Contact Form"
		frameborder="0"
		style="height:800px;width:99%;border:none;"
		src="https://forms.zohopublic.com/davidgonsalves2/form/ContactUs/formperma/kXQbxHB7veB2TrLwryD__KRqHIFzU3z0nxa9KTDfKpQ"
		onload={() => {
			isLoading = false;
			console.log('Form loaded');
		}}
		hidden={isLoading}
	></iframe>
</section>
