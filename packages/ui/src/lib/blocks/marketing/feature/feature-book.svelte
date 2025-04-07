<script lang="ts">
    import { Button } from '../../../components/ui/button/';
    import { BookOpen, ChevronRight } from "lucide-svelte";
    
    type AgeRange = {
        min: number;
        max: number;
    };
    
    let { 
        title = "Featured Story", 
        subtitle = "Join Laifu and Nini as they explore the magical forest and make new friends along the way!", 
        image = "https://placehold.co/500x400", 
        imageAlt = "Laifu and Nini's Big Day Out",
        bookTitle = "Laifu and Nini's Big Day Out",
        ageRange = { min: 4, max: 8 },
        pages = 32,
        price = 12.99,
        viewAllLink = "/books"
    } : { 
        title?: string; 
        subtitle?: string; 
        image?: string; 
        imageAlt?: string;
        bookTitle?: string;
        ageRange?: AgeRange;
        pages?: number;
        price?: number;
        viewAllLink?: string;
    } = $props();
</script>

<section class="px-4 py-8 mx-auto lg:gap-8 xl:gap-0 lg:py-16 ">
    <div class="flex items-center justify-between mb-8">
      <h2 class="text-3xl font-bold text-primary dark:text-white">{title}</h2>
      <a href={viewAllLink} class="text-primary flex items-center hover:underline dark:text-white">
        View all books
        <ChevronRight class="ml-1 h-4 w-4" />
      </a>
    </div>

    <div class="bg-white dark:bg-zinc-800 shadow-lg p-6 md:p-8 grid md:grid-cols-2 gap-8">
      <div class="relative h-[400px] md:h-[500px] rounded-xl overflow-hidden shadow-lg transform -rotate-2 hover:rotate-0 transition-transform duration-300">
        <img
          src={image}
          alt={imageAlt}
          class="object-cover"
        />
      </div>
      <div class="flex flex-col justify-center space-y-6">
        <div>
          <h3 class="text-3xl font-bold text-primary dark:text-white mb-2">{bookTitle}</h3>
          <p class="text-lg text-muted-foreground dark:text-zinc-400">
            {subtitle}
          </p>
        </div>
        <div class="flex items-center gap-4">
          <div class="bg-primary/10 dark:bg-primary/20 px-4 py-2 rounded-full text-primary dark:text-zinc-100 font-medium">Ages {ageRange.min}-{ageRange.max}</div>
          <div class="bg-primary/10 dark:bg-primary/20 px-4 py-2 rounded-full text-primary dark:text-zinc-100 font-medium">{pages} pages</div>
        </div>
        <Button size="lg" class="w-full md:w-auto bg-primary-700 hover:bg-primary-800 focus:ring-4 focus:ring-primary-300 dark:focus:ring-primary-900 text-white">
          <BookOpen class="mr-2 h-5 w-5" />
          Read Preview
        </Button>
        <Button  size="lg" variant="outline" class="w-full md:w-auto border-input bg-background hover:bg-accent hover:text-accent-foreground border">
          Add to Cart - £{price.toFixed(2)}
        </Button>
      </div>
    </div>
  </section>