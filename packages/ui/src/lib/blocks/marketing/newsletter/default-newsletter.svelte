<script lang="ts">
  let {
    // Define the props for the newsletter component
    title = 'Sign up for our newsletter',
    subtitle = 'Stay up to date with the roadmap progress, announcements and exclusive discounts feel free to sign up with your email.',
    buttonText = 'Subscribe',
    privacyPolicyLink = '#',
    privacyPolicyText = 'Read our Privacy Policy'
  }: {
    title: string;
    subtitle: string;
    buttonText: string;
    privacyPolicyLink: string;
    privacyPolicyText: string;
  } = $props();
</script>

<section class="bg-white dark:bg-zinc-900">
  <div class="py-8 px-4 mx-auto max-w-screen-xl lg:py-16 lg:px-6">
    <div class="mx-auto max-w-screen-md sm:text-center">
      <h2
        class="mb-4 text-3xl tracking-tight font-extrabold text-zinc-900 sm:text-4xl dark:text-white"
      >
        {title}
      </h2>
      <p
        class="mx-auto mb-8 max-w-2xl font-light text-zinc-500 md:mb-12 sm:text-xl dark:text-zinc-400"
      >
        {subtitle}
      </p>
      <form action="#">
        <div class="items-center mx-auto mb-3 space-y-4 max-w-screen-sm sm:flex sm:space-y-0">
          <div class="relative w-full">
            <label
              for="email"
              class="hidden mb-2 text-sm font-medium text-zinc-900 dark:text-zinc-300"
              >Email address</label
            >
            <div class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none">
              <svg
                class="w-5 h-5 text-zinc-500 dark:text-zinc-400"
                fill="currentColor"
                viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg"
                ><path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"
                ></path><path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"
                ></path></svg
              >
            </div>
            <input
              class="block p-3 pl-10 w-full text-sm text-zinc-900 bg-zinc-50 rounded-lg border border-zinc-300 sm:rounded-none sm:rounded-l-lg focus:ring-primary-500 focus:border-primary-500 dark:bg-zinc-700 dark:border-zinc-600 dark:placeholder-zinc-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
              placeholder="Enter your email"
              type="email"
              id="email"
              required
            />
          </div>
          <div>
            <button
              type="submit"
              class="py-3 px-5 w-full text-sm font-medium text-center text-white rounded-lg border cursor-pointer bg-primary-700 border-primary-600 sm:rounded-none sm:rounded-r-lg hover:bg-primary-800 focus:ring-4 focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800"
            >
              {buttonText}
            </button>
          </div>
        </div>
        <div
          class="mx-auto max-w-screen-sm text-sm text-left text-zinc-500 newsletter-form-footer dark:text-zinc-300"
        >
          {privacyPolicyText}
          <a
            href={privacyPolicyLink}
            class="font-medium text-primary-600 dark:text-primary-500 hover:underline"
            >Read our Privacy Policy</a
          >.
        </div>
      </form>
    </div>
  </div>
</section>
