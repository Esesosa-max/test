<script>
  import { onMount } from "svelte";

  import Nav from "./_Nav.svelte";
  onMount(() => M.AutoInit());
  export let segment;
</script>

<Nav {segment} />

<slot />
