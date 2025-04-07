<script lang="ts">
    import { Button } from '@monorepo/ui/components/ui/button';
    import Header from './Header.svelte';
</script>

<Header />
<main class="flex flex-col items-center justify-center min-h-screen p-4">
    <h1 class="text-3xl font-bold">Welcome to Laifu and Nini!</h1>
    <p class="mt-4 text-lg">This is a simple SvelteKit app.</p>
    <Button variant="default" class="mt-4">Click Me!</Button>
    <p class="mt-4 text-sm text-zinc-500">This is a simple SvelteKit app.</p>
</main>
