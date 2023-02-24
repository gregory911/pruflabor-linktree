<script lang="ts">
  import { Router, Route } from "svelte-routing";

  import Links from "./views/Links.svelte";
  import RudeOofClairons from "./views/RudeOofClairons.svelte";
  import Harmonie from "./views/Harmonie.svelte";
  import UnSubtilZesteDeChaos from "./views/UnSubtilZesteDeChaos.svelte";

  export let url = "";
</script>

<Router {url}>
  <!-- Albums -->
  <Route path="/rude-oof-clairons" component={RudeOofClairons} />
  <Route path="/harmonie" component={Harmonie} />
  <Route path="/un-subtil-zeste-de-chaos" component={UnSubtilZesteDeChaos} />

  <!-- Landing page -->
  <Route path="/" component={Links} />
</Router>

<style>

</style>
