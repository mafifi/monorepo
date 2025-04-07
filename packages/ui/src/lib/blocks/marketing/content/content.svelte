<script lang="ts">
	import type { HTMLImgAttributes, HTMLAnchorAttributes } from 'svelte/elements';
	let {
		title = 'Turn on collaboration into innovation',
		tagline,
		contentCards = []
	}: {
		title: string;
		tagline?: HTMLAnchorAttributes;
		contentCards?: {
			image?: HTMLImgAttributes;
			title: string;
			description: string;
		}[];
	} = $props();
</script>

<section class="bg-white dark:bg-gray-900">
	<div class="mx-auto max-w-screen-xl px-4 py-8 lg:px-6 lg:py-16">
		<div class="text-center text-gray-900">
			<h2
				class="mb-4 text-4xl font-extrabold tracking-tight text-gray-900 lg:text-5xl dark:text-white">
				{title}
			</h2>
			{#if tagline}
				<a
					href={tagline.href}
					class="text-primary-600 hover:text-primary-800 dark:text-primary-500 dark:hover:text-primary-700 inline-flex items-center text-lg font-medium">
					{tagline.title}
					<svg
						class="ml-1 h-6 w-6"
						fill="currentColor"
						viewBox="0 0 20 20"
						xmlns="http://www.w3.org/2000/svg"
						><path
							fill-rule="evenodd"
							d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
							clip-rule="evenodd"></path
						></svg>
				</a>
			{/if}
		</div>
		{#if contentCards.length > 0}
			<div class="mt-12 grid gap-6 md:grid-cols-3 lg:mt-14 lg:gap-12">
				{#each contentCards as card}
					<div class="mb-2 flex md:mb-0 md:flex-col">
						{#if card.image}
							<img
								class="mr-4 h-36 w-auto rounded-lg md:h-auto md:w-full"
								src={card.image.src}
								alt={card.image.alt} />
						{/if}

						<div>
							<h3 class="mb-2.5 text-xl font-bold text-gray-900 md:mt-4 dark:text-white">
								{card.title}
							</h3>
							<p class="text-gray-500 dark:text-gray-400">
								{card.description}
							</p>
						</div>
					</div>
				{/each}
			</div>
		{/if}
	</div>
</section>
