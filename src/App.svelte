<script>
  import Nav from "./components/Nav.svelte";
  import Home from "./pages/Home.svelte";
  import Experience from "./pages/Experience.svelte";
  import Projects from "./pages/Projects.svelte";
  import Awards from "./pages/Awards.svelte";

  const navlinks = [
    { displayName: "Home", href: "#home", id: "home" },
    { displayName: "Awards and Education ", href: "#awards", id: "awards" },
    { displayName: "Experience", href: "#experience", id: "experience" },
    { displayName: "Ongoing projects", href: "#projects", id: "projects" },
  ];
</script>

<style>
  main {
    font-size: 16px;
  }
</style>

<main>
  <Nav {navlinks} />
  <div class="container-fluid p-0">
    <Home />
    <Awards />
    <Experience />
    <Projects />
  </div>
</main>
