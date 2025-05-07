<script lang="ts">
	import { X } from 'lucide-svelte';
</script>

{#snippet policyLinks(href: string, text: string)}
	<a
		{href}
		class="text-text-light hover:shadow-button-hover-shadow inline-block rounded-lg bg-gradient-to-r from-purple-600 to-indigo-500 px-8 py-3 font-bold uppercase shadow-lg transition-all duration-300 hover:scale-105 hover:bg-indigo-700 active:scale-95"
	>
		{text}
	</a>
{/snippet}
<footer
	class="flex flex-col items-center justify-center gap-4 py-12 text-center text-sm text-gray-500"
>
	<p>
		&copy;
		{new Date().getFullYear()}
		Scalable Logix. All rights reserved.
	</p>

	<div class="mt-2 flex flex-wrap justify-center gap-4">
		{@render policyLinks('/#/terms-of-service', 'Terms of Service')}

		{@render policyLinks('/#/privacy-policy', 'Privacy Policy')}

		{@render policyLinks('/#/refund-policy', 'Refund Policy')}
	</div>
	<!-- Social Links -->
	<div class="flex items-center justify-center">
		<div class="rounded bg-white p-2">
			<a href="https://x.com/Davi_g117" aria-label="Twitter" target="_blank">
				<svg
					xmlns="http://www.w3.org/2000/svg"
					x="0px"
					y="0px"
					width="30"
					height="30"
					viewBox="0 0 50 50"
				>
					<path
						d="M 11 4 C 7.134 4 4 7.134 4 11 L 4 39 C 4 42.866 7.134 46 11 46 L 39 46 C 42.866 46 46 42.866 46 39 L 46 11 C 46 7.134 42.866 4 39 4 L 11 4 z M 13.085938 13 L 21.023438 13 L 26.660156 21.009766 L 33.5 13 L 36 13 L 27.789062 22.613281 L 37.914062 37 L 29.978516 37 L 23.4375 27.707031 L 15.5 37 L 13 37 L 22.308594 26.103516 L 13.085938 13 z M 16.914062 15 L 31.021484 35 L 34.085938 35 L 19.978516 15 L 16.914062 15 z"
					></path>
				</svg>
			</a>
		</div>
	</div>
</footer>
