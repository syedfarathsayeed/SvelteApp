<script>
  import Library from "./Library/Library.svelte";
  import { Route, Router } from "svelte-routing";
  import Detail from "./Detail/Detail.svelte";
  import Create from "./Create/Create.svelte"
  export let url = "";
</script>

<style>
  main {
    padding: var(--spacingLarge);
  }
</style>

<Router {url}>
  <main>
    <Route path="/create">
      <Create />
    </Route>
    <Route path="/">
      <Library />
    </Route>
    <Route path="/books/:id" let:params>
      <Detail id={params.id} />
    </Route>
  </main>
</Router>
