<script lang="ts">
	import type { Snippet } from 'svelte';

	type feature = {
		title: string;
		description: string;
		icon: Snippet;
		primaryButton?: {
			href: HTMLAnchorElement['href'];
			title: HTMLAnchorElement['title'];
		};
	};

	type imageProps = {
		src: HTMLImageElement['src'];
		alt: HTMLImageElement['alt'];
	};

	let {
		title,
		description,
		image,
		features = []
	}: {
		title: string;
		description: string;
		image: imageProps;
		features: feature[];
	} = $props();
</script>

<section class="bg-white dark:bg-gray-900">
	<div
		class="mx-auto max-w-screen-xl items-center gap-8 px-4 py-8 sm:py-16 lg:grid lg:grid-cols-2 lg:px-6 xl:gap-16">
		<img class="mb-4 w-full rounded-lg lg:mb-0" src={image.src} alt={image.alt} />
		<div class="text-gray-500 sm:text-lg dark:text-gray-400">
			<h2 class="mb-4 text-4xl font-extrabold tracking-tight text-gray-900 dark:text-white">
				{title}
			</h2>
			<p class="mb-8 font-light lg:text-xl">
				{description}
			</p>
			<div class="mb-6 border-t border-b border-gray-200 py-8 dark:border-gray-700">
				{#each features as feature}
					<div class="flex pt-8">
						<div
							class="mr-4 flex h-8 w-8 shrink-0 items-center justify-center rounded-full bg-gray-100 dark:bg-gray-900">
							{@render feature.icon()}
						</div>
						<div>
							<h3 class="mb-2 text-xl font-bold text-gray-900 dark:text-white">{feature.title}</h3>
							<p class="mb-2 font-light text-gray-500 dark:text-gray-400">
								{feature.description}
							</p>
							{#if feature.primaryButton}
								<a
									href={feature.primaryButton.href}
									class="text-primary-600 hover:text-primary-800 dark:text-primary-500 dark:hover:text-primary-600 inline-flex items-center">
									{feature.primaryButton.title}
									<svg
										class="ml-1 h-6 w-6"
										fill="currentColor"
										viewBox="0 0 20 20"
										xmlns="http://www.w3.org/2000/svg">
										<path
											fill-rule="evenodd"
											d="M7.293 14.707a1 1 0 010-1.414L10.586 10l-3.293-3.293a1 1 0 011.414-1.414l4 4a1 1 0 010 1.
                                            414l-4 4a1 1 0 01-1.414 0z"
											clip-rule="evenodd"></path
										></svg>
								</a>
							{/if}
						</div>
					</div>
				{/each}
			</div>
			<p class="text-sm">
				Deliver great service experiences fast - without the complexity of traditional ITSM
				solutions.Accelerate critical development work, eliminate toil, and deploy changes with
				ease.
			</p>
		</div>
	</div>
</section>
