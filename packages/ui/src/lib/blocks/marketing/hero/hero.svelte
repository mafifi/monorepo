<script lang="ts">
    type Link = {
        href: string;
        text: string;
        isPrimary?: boolean;
    };
    let {
        title = "Payments tool for software companies",
        subtitle = "From checkout to global sales tax compliance, companies around the world use Flowbite to simplify their payment stack.",
        image = "https://flowbite.s3.amazonaws.com/blocks/marketing-ui/hero/phone-mockup.png",
        imageAlt = "mockup",
        links = [
            { href: "#", text: "Get started", isPrimary: true },
            { href: "#", text: "Speak to Sales", isPrimary: false }
        ]
    } : {
        title?: string;
        subtitle?: string;
        image?: string;
        imageAlt?: string;
        links?: Link[];
    } = $props();

</script>

<section class="bg-white dark:bg-zinc-900">
    <div class="grid px-4 py-8 mx-auto lg:gap-8 xl:gap-0 lg:py-16 lg:grid-cols-12">
        <div class="mr-auto place-self-center lg:col-span-7">
            <h1 class="max-w-2xl mb-4 text-4xl font-extrabold tracking-tight leading-none md:text-5xl xl:text-6xl dark:text-white">{title}</h1>
            <p class="max-w-2xl mb-6 font-light text-zinc-500 lg:mb-8 md:text-lg lg:text-xl dark:text-zinc-400">{subtitle}</p>
            
            {#each links as link, i}
                {#if link.isPrimary}
                    <a href={link.href} class="inline-flex items-center justify-center px-5 py-3 mr-3 text-base font-medium text-center text-white rounded-lg bg-primary-700 hover:bg-primary-800 focus:ring-4 focus:ring-primary-300 dark:focus:ring-primary-900">
                        {link.text}
                        <svg class="w-5 h-5 ml-2 -mr-1" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
                    </a>
                {:else}
                    <a href={link.href} class="inline-flex items-center justify-center px-5 py-3 text-base font-medium text-center text-zinc-900 border border-zinc-300 rounded-lg hover:bg-zinc-100 focus:ring-4 focus:ring-zinc-100 dark:text-white dark:border-zinc-700 dark:hover:bg-zinc-700 dark:focus:ring-zinc-800">
                        {link.text}
                    </a> 
                {/if}
            {/each}
        </div>
        <div class="hidden lg:mt-0 lg:col-span-5 lg:flex">
            <img src={image} alt={imageAlt}>
        </div>                
    </div>
</section>