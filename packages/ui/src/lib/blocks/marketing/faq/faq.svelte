<script lang="ts">
	import type { Snippet } from 'svelte';

	type FAQ = {
		question: string;
		answer: string | Snippet;
	};

	let { title, faqs = [] }: { title: string; faqs: FAQ[] } = $props();
</script>

<section class="bg-white dark:bg-gray-900">
	<div class="mx-auto max-w-screen-xl px-4 py-8 sm:py-16 lg:px-6">
		<h2
			class="mb-6 text-center text-3xl font-extrabold tracking-tight text-gray-900 lg:mb-8 lg:text-4xl dark:text-white">
			{title}
		</h2>
		<div class="mx-auto max-w-screen-md">
			<div
				id="accordion-flush"
				data-accordion="collapse"
				data-active-classes="bg-white dark:bg-gray-900 text-gray-900 dark:text-white"
				data-inactive-classes="text-gray-500 dark:text-gray-400">
				{#each faqs as faq, index}
					<h2 id="accordion-flush-heading-{index}">
						<button
							type="button"
							class="flex w-full items-center justify-between border-b border-gray-200 bg-white py-5 text-left font-medium text-gray-900 dark:border-gray-700 dark:bg-gray-900 dark:text-white"
							data-accordion-target="#accordion-flush-body-{index}"
							aria-expanded="true"
							aria-controls="accordion-flush-body-{index}">
							<span>{faq.question}</span>
							<svg
								data-accordion-icon=""
								class="h-6 w-6 shrink-0 rotate-180"
								fill="currentColor"
								viewBox="0 0 20 20"
								xmlns="http://www.w3.org/2000/svg"
								><path
									fill-rule="evenodd"
									d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
									clip-rule="evenodd"></path
								></svg>
						</button>
					</h2>
					<div
						id="accordion-flush-body-{index}"
						class=""
						aria-labelledby="accordion-flush-heading-{index}">
						<div class="border-b border-gray-200 py-5 dark:border-gray-700">
							{#if typeof faq.answer === 'function'}
								{@render faq.answer()}
							{:else}
								<p class="mb-2 text-gray-500 dark:text-gray-400">
									{faq.answer}
								</p>
							{/if}
						</div>
					</div>
				{/each}
			</div>
		</div>
	</div>
</section>
