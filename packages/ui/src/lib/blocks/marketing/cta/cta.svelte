<script lang="ts">
	type anchorProps = {
		href: HTMLAnchorElement['href'];
		title: HTMLAnchorElement['title'];
	};

	let {
		title = "Let's find more that brings us together.",
		description = 'Flowbite helps you connect with friends, family and communities of people who share your interests. Connecting with your friends and family as well as discovering new ones is easy with features like Groups, Watch and Marketplace.',
		primaryButton,
		secondaryButton
	}: {
		title: string;
		description: string;
		primaryButton: anchorProps;
		secondaryButton: anchorProps;
	} = $props();
</script>

<section class="bg-white dark:bg-gray-900">
	<div class="mx-auto max-w-screen-xl px-4 py-8 sm:py-16 lg:px-6">
		<div class="max-w-screen-md">
			<h2 class="mb-4 text-4xl font-extrabold tracking-tight text-gray-900 dark:text-white">
				{title}
			</h2>
			<p class="mb-8 font-light text-gray-500 sm:text-xl dark:text-gray-400">
				{description}
			</p>
			<div class="flex flex-col space-y-4 sm:flex-row sm:space-y-0 sm:space-x-4">
				<a
					href={primaryButton.href}
					class="bg-primary-700 hover:bg-primary-800 focus:ring-primary-300 dark:focus:ring-primary-900 inline-flex items-center justify-center rounded-lg px-4 py-2.5 text-center text-base font-medium text-white focus:ring-4">
					{primaryButton.title}
				</a>
				<a
					href={secondaryButton.href}
					class="inline-flex items-center justify-center rounded-lg border border-gray-300 px-4 py-2.5 text-center text-base font-medium text-gray-900 hover:bg-gray-100 focus:ring-4 focus:ring-gray-100 dark:border-gray-600 dark:text-white dark:hover:bg-gray-700 dark:focus:ring-gray-600">
					<svg
						class="mr-2 -ml-1 h-5 w-5"
						fill="currentColor"
						viewBox="0 0 20 20"
						xmlns="http://www.w3.org/2000/svg"
						><path
							d="M2 6a2 2 0 012-2h6a2 2 0 012 2v8a2 2 0 01-2 2H4a2 2 0 01-2-2V6zM14.553 7.106A1 1 0 0014 8v4a1 1 0 00.553.894l2 1A1 1 0 0018 13V7a1 1 0 00-1.447-.894l-2 1z"
						></path
						></svg>
					{secondaryButton.title}
				</a>
			</div>
		</div>
	</div>
</section>
