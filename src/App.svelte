<script>
  import Awards from "./components/Awards.svelte";
  import Nav from "./components/Nav.svelte";
  import Experience from "./components/Experience.svelte";
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
    <Experience />
    <Awards />
  </div>
</main>
