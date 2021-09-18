<script>
  import { getAuth, onAuthStateChanged } from "@firebase/auth";
  import { onMount } from "svelte";
  import { app } from "./_config.svelte";
  export let segment;
  let user2;
  onMount(() => {
    onAuthStateChanged(getAuth(app), (user) => {
      if (user) {
        user2 = user;
      } else {
      }
    });
  });
</script>

{#if segment !== "admin"}
  <nav class="purple">
    <div class="nav-wrapper container">
      <a href="/" class="brand-logo">Tech Upfront</a>
      <a href="/" data-target="mobile-demo" class="sidenav-trigger"
        ><i class="material-icons">menu</i></a
      >
      <ul class="right hide-on-med-and-down">
        {#if user2}
          <li><a href="/admin">Admin</a></li>
        {/if}
        <li><a href="/about">About</a></li>
      </ul>
    </div>
  </nav>

  <ul class="sidenav" id="mobile-demo">
    <li><a href="/about">About</a></li>
  </ul>
{/if}
