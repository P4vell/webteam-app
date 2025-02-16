<script lang="ts">
  import {Menu, X} from 'lucide-svelte';
  import {NAVIGATION_LINKS} from '$constants'
  import { cn } from '$lib';

  let isMobileMenuOpen = $state(false);

  const toggleMobileMenu = () => {
    isMobileMenuOpen = !isMobileMenuOpen;
  }
</script>

<div class="md:hidden">
  <button 
    class="w-10 h-10 inline-flex justify-center items-center text-sm text-zinc-800 font-medium rounded-md px-3 cursor-pointer hover:bg-zinc-100" 
    onclick={toggleMobileMenu}
    aria-expanded={isMobileMenuOpen}
    aria-controls="mobile-menu"
    >
    {#if isMobileMenuOpen}
      <X />
    {:else}
      <Menu />
    {/if}
  </button>

  <nav id="mobile-menu" class={cn("w-full h-screen absolute left-0 top-0 bg-white -translate-y-full transition-transform duration-300 ease-in-out", {
    "top-14 translate-y-0": isMobileMenuOpen
  })}>
    <ul class="p-10">
      {#each NAVIGATION_LINKS as {label, href}}
      <li class="py-3">
        <a {href} class="w-full h-9 inline-flex justify-center items-center text-lg text-zinc-800 font-medium rounded-md px-3 hover:bg-zinc-100">
          {label}
        </a>
      </li>
    {/each}
    </ul>
  </nav>
</div>