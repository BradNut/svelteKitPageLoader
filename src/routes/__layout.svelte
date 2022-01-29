<script lang="ts">
  import { navigating } from '$app/stores';
  
  import { loading } from '$lib/loading';
  import Loading from '$lib/Loading.svelte';

  $: $loading = !!$navigating;
</script>

{$loading}

<slot />

<button on:click={() => $loading = true}>Set Loading</button>

<button on:click={() => $loading = false}>Stop Loading</button>

<Loading />