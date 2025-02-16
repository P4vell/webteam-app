<script lang="ts">
  import Navigation from "$components/molecules/navigation.svelte";
  let {children} = $props();
  import "../app.css";
</script>

<Navigation />
<main class="min-h-screen bg-neutral-100">
  {@render children()}
</main>