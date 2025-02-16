<script lang="ts">
  import MobileMenu from "./mobile-menu.svelte";
  import {NAVIGATION_LINKS} from '$constants'
</script>

<header class="h-16 sticky top-0 inset-x-0 bg-white/75 border-b border-gray-200 backdrop-blur-lg z-10">
  <nav class="w-full h-full max-w-screen-xl flex justify-between items-center px-2.5 mx-auto md:px-20">
    <a href="/" class="text-lg font-bold">Webteam app</a>

    <ul class="hidden items-center gap-4 md:flex">
      {#each NAVIGATION_LINKS as {label, href}}
        <li>
          <a {href} class="h-9 inline-flex justify-center items-center text-sm text-zinc-800 font-medium rounded-md px-3 hover:bg-zinc-100">
            {label}
          </a>
        </li>
      {/each}
    </ul>

    <MobileMenu />
  </nav>
</header>