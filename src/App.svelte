<script>
  import { ScrollableSection, ScrollSpy } from "@beyonk/svelte-scrollspy";

  import Nav from "./components/Nav.svelte";
  import Home from "./components/Home.svelte";
  import Experience from "./components/Experience.svelte";
  import Awards from "./components/Awards.svelte";
</script>

<style>
  main {
    font-size: 16px;
  }
</style>

<main>
  <ScrollSpy>
    <Nav />
    <div class="container-fluid p-0">
      <Home />
      <Experience />
      <Awards />
    </div>
  </ScrollSpy>
</main>
