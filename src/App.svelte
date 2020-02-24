<script>
  import Nav from "./components/Nav.svelte";
  import Home from "./components/Home.svelte";
</script>

<style>
  main {
    font-size: 16px;
  }
</style>

<main>
  <Nav />
  <div class="container-fluid p-0">
    <Home />
  </div>
</main>
