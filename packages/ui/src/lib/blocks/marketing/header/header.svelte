<script lang="ts">
    type MenuItem = {
        name: string;
        href: string;
        image?: string;
    };

    type Image = {
        src: string;
        alt: string;
    };
    
    type HeaderProps = {
        menus: MenuItem[];
        logo?: {
            image: Image;
            text: string;
            href: string;
        };
        actions?: {
            login?: {
                text: string;
                href: string;
            };
            signup?: {
                text: string;
                href: string;
            };
        };
        activeItem?: string;
    };

    let { 
        menus, 
        logo = {
            image: { src: "", alt: "Logo" },
            text: "",
            href: "/"
        },
        actions = {
            login: { text: "Log in", href: "#" },
            signup: { text: "Get started", href: "#" }
        },
        activeItem = "Home"
    }: HeaderProps = $props();

</script>

<header>
    <nav class="bg-white border-zinc-200 px-4 lg:px-6 py-2.5 dark:bg-zinc-800">
        <div class="flex flex-wrap justify-between items-center mx-auto max-w-screen-xl">
            <a href={logo.href} class="flex items-center">
                {#if logo.image.src}
                    <img src={logo.image.src} class="mr-3 h-6 sm:h-9" alt={logo.image.alt} />
                {/if}
                {#if logo.text}
                    <span class="self-center text-xl font-semibold whitespace-nowrap dark:text-white">{logo.text}</span>
                {/if}
            </a>
            <div class="flex items-center lg:order-2">
                {#if actions.login}
                    <a href={actions.login.href} class="text-zinc-800 dark:text-white hover:bg-zinc-50 focus:ring-4 focus:ring-zinc-300 font-medium rounded-lg text-sm px-4 lg:px-5 py-2 lg:py-2.5 mr-2 dark:hover:bg-zinc-700 focus:outline-none dark:focus:ring-zinc-800">{actions.login.text}</a>
                {/if}
                {#if actions.signup}
                    <a href={actions.signup.href} class="text-white bg-primary-700 hover:bg-primary-800 focus:ring-4 focus:ring-primary-300 font-medium rounded-lg text-sm px-4 lg:px-5 py-2 lg:py-2.5 mr-2 dark:bg-primary-600 dark:hover:bg-primary-700 focus:outline-none dark:focus:ring-primary-800">{actions.signup.text}</a>
                {/if}
                <button data-collapse-toggle="mobile-menu-2" type="button" class="inline-flex items-center p-2 ml-1 text-sm text-zinc-500 rounded-lg lg:hidden hover:bg-zinc-100 focus:outline-none focus:ring-2 focus:ring-zinc-200 dark:text-zinc-400 dark:hover:bg-zinc-700 dark:focus:ring-zinc-600" aria-controls="mobile-menu-2" aria-expanded="false">
                    <span class="sr-only">Open main menu</span>
                    <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z" clip-rule="evenodd"></path></svg>
                    <svg class="hidden w-6 h-6" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
                </button>
            </div>
            <div class="hidden justify-between items-center w-full lg:flex lg:w-auto lg:order-1" id="mobile-menu-2">
                <ul class="flex flex-col mt-4 font-medium lg:flex-row lg:space-x-8 lg:mt-0">
                    {#each menus as menu}
                        <li>
                            <a href={menu.href} 
                               class={`block py-2 pr-4 pl-3 ${menu.name === activeItem ? 
                               'text-white rounded bg-primary-700 lg:bg-transparent lg:text-primary-700 lg:p-0 dark:text-white' : 
                               'text-zinc-700 border-b border-zinc-100 hover:bg-zinc-50 lg:hover:bg-transparent lg:border-0 lg:hover:text-primary-700 lg:p-0 dark:text-zinc-400 lg:dark:hover:text-white dark:hover:bg-zinc-700 dark:hover:text-white lg:dark:hover:bg-transparent dark:border-zinc-700'}`}
                               aria-current={menu.name === activeItem ? 'page' : undefined}>
                                {menu.name}
                            </a>
                        </li>
                    {/each}
                </ul>
            </div>
        </div>
    </nav>
</header>