<script lang="ts">
    import { Header } from '@monorepo/ui/blocks/marketing/header';
    import { page } from '$app/state';
    
    // Define reactive variables using Svelte 5 Runes syntax
    const path = $derived(page.url.pathname);
    const activeItem = $derived(getActiveItem(path));
    
    function getActiveItem(path: string): string {
        // Exact matches
        if (path === '/') return 'Home';
        if (path === '/books') return 'All Books';
        if (path === '/about') return 'About';
        if (path === '/contact') return 'Contact';
        
        // Check for path patterns
        if (path.startsWith('/books/')) return 'All Books';
        
        return 'Home'; // Default fallback
    }
</script>

<Header
  menus={[
    { name: 'Home', href: '/' },
    { name: 'All Books', href: '/books' },
    { name: 'About', href: '/about' },
    { name: 'Contact', href: '/contact' }
  ]}
  logo={{
    image: {
      src: 'https://placehold.co/40x40',
      alt: 'Laifu and Nini logo'
    },
    text: 'Laifu and Nini',
    href: '/'
  }}
  actions={{
    login: { text: 'Log in', href: '#' },
    signup: { text: 'Get started', href: '#' }
  }}
  activeItem={activeItem}
/>