<script lang="ts">
    type ContentCard = {
        link: string;
        image?: {
            src: string;
            alt: string;
        };
        title: string;
        description: string;
    };

    let { 
        title = 'Turn on collaboration into innovation', 
        contentCards = [] 
    }: { 
        title: string; 
        contentCards?: ContentCard[]; 
    } = $props();

</script>

<section class="bg-white dark:bg-zinc-900">
    <div class="py-8 px-4 mx-auto max-w-screen-xl lg:py-16 lg:px-6">
        <div class="text-center text-zinc-900">
            <h2 class="mb-4 text-4xl tracking-tight font-extrabold text-zinc-900 lg:text-5xl dark:text-white">
                {title}
            </h2>
        </div>
        <div class="grid gap-6 mt-12 lg:mt-14 lg:gap-12 md:grid-cols-3">
            {#each contentCards as card}
                <a class="mb-2 flex md:mb-0 md:flex-col aspect-[3/4] "
                    href={card.link}>
                    {#if card.image}
                        <img class="mr-4 w-auto h-36 md:w-full md:h-auto rounded-lg hover:shadow-xl transition-all duration-300 hover:-translate-y-2" src={card.image.src} alt={card.image.alt} />
                    {/if}
                    <div>
                        <h3 class="text-xl font-bold md:mt-4 mb-2.5 text-zinc-900 dark:text-white">{card.title}</h3>
                        <p class="text-zinc-500 dark:text-zinc-400">{card.description}</p>
                    </div>
                </a>
            {/each}
        </div>
    </div>
  </section>