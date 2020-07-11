<script>
  import Nav from "./components/Nav.svelte";
  import Home from "./pages/Home.svelte";
  import Experience from "./pages/Experience.svelte";
  import Projects from "./pages/Projects.svelte";
  import Awards from "./pages/Awards.svelte";
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
    <Awards />
    <Experience />
    <Projects />
  </div>
</main>
