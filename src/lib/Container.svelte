<script>
  import { mode } from "../shared.svelte";
  import Grid from "./Grid.svelte";
</script>

<div class="container" class:dark={mode.theme === "dark"}>
  <div class="wrapper">
    <Grid></Grid>
    <slot></slot>
  </div>
</div>

<style>
  .container {
    --bg: #e9e9e9;
    --fg: #14231c;
    width: 100%;
    background-color: var(--bg);
    color: var(--fg);
    padding: 0 1rem;
  }
  .container.dark {
    --bg: #14231c;
    --fg: #e9e9e9;
  }
  .wrapper {
    max-width: 1450px;
    margin: 0 auto;
    position: relative;
  }
</style>
