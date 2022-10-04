<script>
  import Section from "../components/Section.svelte";

  const projects = [
    {
      name: "Dotsy",
      description: `A dotfile manager inspired by dotbot written in rust`,
      source: "https://github.com/NICHTJ3/Dotsy",
    },
  ];
</script>

<style>
  .social-icons a {
    display: inline-block;
    height: 2rem;
    width: 2rem;
    background-color: #495057;
    color: #fff !important;
    border-radius: 100%;
    text-align: center;
    font-size: 1.5rem;
    line-height: 2.1rem;
    margin-right: 0.5rem;
  }

  .social-icons a:hover {
    background-color: #add8e6;
  }

  a:hover,
  a:focus,
  a:active {
    text-decoration: none;
    color: inherit !important;
  }
</style>

<Section sectionId="projects">
  <h2 class="mb-3">What I'm up to at the moment</h2>

  {#each projects as project}
    <div class="resume-item d-flex flex-column justify-content-between mb-3">
      <div class="resume-content">
        <h4 class="m-0">
          <span class="social-icons">
            <a href={project.source}>
              <i class="fab fa-github" />
            </a>
          </span>
          <a class="text-primary link" href={project.source}>{project.name}</a>
        </h4>
      </div>
      <p>{project.description}</p>
    </div>
  {/each}

</Section>
