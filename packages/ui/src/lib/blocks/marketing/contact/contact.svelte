<script lang="ts">
	let {
		title = 'Contact Us',
		description = 'Got a technical issue? Want to send feedback about a beta feature? Need details about our Business plan? Let us know.',
		emailPlaceholder = '',
		subjectPlaceholder = 'Let us know how we can help you',
		messagePlaceholder = 'Leave a comment...',
		buttonText = 'Send message'
	}: {
		title: string;
		description: string;
		emailPlaceholder: string;
		subjectPlaceholder: string;
		messagePlaceholder: string;
		buttonText: string;
	} = $props();
</script>

<section class="bg-white dark:bg-gray-900">
	<div class="mx-auto max-w-screen-md px-4 py-8 lg:py-16">
		<h2
			class="mb-4 text-center text-4xl font-extrabold tracking-tight text-gray-900 dark:text-white">
			{title}
		</h2>
		<p class="mb-8 text-center font-light text-gray-500 sm:text-xl lg:mb-16 dark:text-gray-400">
			{description}
		</p>
		<form action="#" class="space-y-8">
			<div>
				<label for="email" class="mb-2 block text-sm font-medium text-gray-900 dark:text-gray-300"
					>Your email</label>
				<input
					type="email"
					id="email"
					class="focus:ring-primary-500 focus:border-primary-500 dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light block w-full rounded-lg border border-gray-300 bg-gray-50 p-2.5 text-sm text-gray-900 shadow-sm dark:border-gray-600 dark:bg-gray-700 dark:text-white dark:placeholder-gray-400"
					placeholder={emailPlaceholder}
					required />
			</div>
			<div>
				<label for="subject" class="mb-2 block text-sm font-medium text-gray-900 dark:text-gray-300"
					>Subject</label>
				<input
					type="text"
					id="subject"
					class="focus:ring-primary-500 focus:border-primary-500 dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light block w-full rounded-lg border border-gray-300 bg-gray-50 p-3 text-sm text-gray-900 shadow-sm dark:border-gray-600 dark:bg-gray-700 dark:text-white dark:placeholder-gray-400"
					placeholder={subjectPlaceholder}
					required />
			</div>
			<div class="sm:col-span-2">
				<label for="message" class="mb-2 block text-sm font-medium text-gray-900 dark:text-gray-400"
					>Your message</label>
				<textarea
					id="message"
					rows="6"
					class="focus:ring-primary-500 focus:border-primary-500 dark:focus:ring-primary-500 dark:focus:border-primary-500 block w-full rounded-lg border border-gray-300 bg-gray-50 p-2.5 text-sm text-gray-900 shadow-sm dark:border-gray-600 dark:bg-gray-700 dark:text-white dark:placeholder-gray-400"
					placeholder={messagePlaceholder}></textarea>
			</div>
			<button
				type="submit"
				class="bg-primary-700 hover:bg-primary-800 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800 rounded-lg px-5 py-3 text-center text-sm font-medium text-white focus:ring-4 focus:outline-none sm:w-fit"
				>{buttonText}</button>
		</form>
	</div>
</section>
