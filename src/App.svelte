<script>
  import Home from "@/components/Home.svelte";
  import { Core } from "snel";

  export let Request = {};

  const { MatchRoute } = Core;
</script>

{#if MatchRoute("/", Request?.PathName)}
  <Home name={"World"} />
{:else}
  <main>
    <h1>404 not found</h1>
  </main>
{/if}

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
