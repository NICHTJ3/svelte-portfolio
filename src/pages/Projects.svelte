<script>
  import Section from "../components/Section.svelte";

  const projects = [
    {
      name: "Media Analytics",
      description: `A media analytics site created to give an
      accessible interface for data and statistics collected
      and calculated using data from various media outlets. The site is
      currently down but the code is still available. If you want to know more
      have a look at the github repo's wiki`,
      source: "https://github.com/op-analytics/Media-Analytics",
    },
    {
      name: "My Portfolio",
      description: `The portfolio site you're on right now. Created with svelte
      and deployed with ZEIT Now`,
      source: "https://github.com/NICHTJ3/svelte-portfolio",
    },
    {
      name: "Giphy API frontends",
      description: `A bunch of frontends writen for the giphy search API
      endpoint writen in all kinds of frameworks in all sorts of different ways`,
      source: "https://github.com/NICHTJ3/giphy-api-front-ends",
    },
    {
      name: "Vim Markdown Preview",
      description: `A basic yet useful markdown previewing website
        with an embedded vim based text editor for those of us
        who don't want an extra application`,
      source: "https://github.com/NICHTJ3/vim-markdown-renderer",
    },
    {
      name: "Another Social Media",
      description: `The name pretty much says it
      all but this is a social media inspired by twitter
      that i am creating as a playground to try out new and interesting things.`,
      source: "https://github.com/NICHTJ3/AnotherSocialMedia",
    },
    {
      name: "Notesy",
      description: `A note taking app being built as an extension of the Vim
      Markdown Preview project. It's purpose is to provide a well rounded
      minimal note keeping experience like one note but with vim keybindings
      and less bells and whistles`,
      source: "https://github.com/NICHTJ3/notesy-mono-repo/",
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
  <h2 class="mb-3">Ongoing Projects</h2>

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
