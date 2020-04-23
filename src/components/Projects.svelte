<script>
  import { activeSection } from "../store.js";

  const projects = [
    {
      name: "Vim Markdown Preview",
      description: `A basic yet useful markdown previewing website
        with an embedded vim based text editor for those of us
        who don't want an extra application`,
      source: "https://github.com/NICHTJ3/vim-markdown-renderer"
    },
    {
      name: "Another social media",
      description: `The name pretty much says it
      all but this is a social media inspired by twitter
      that i am creating as a playground to try out new and interesting things.`,
      source: "https://github.com/NICHTJ3/AnotherSocialMedia"
    }
  ];

  let observer = new IntersectionObserver(onIntersect, {
    threshold: 0.8
  });

  function onIntersect([section]) {
    if (section.isIntersecting) {
      activeSection.set("projects");
    }
  }

  function observe(node) {
    observer && observer.observe(node);
    return {
      destroy() {
        observer && observer.unobserve(node);
      }
    };
  }
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
    font-size: 1.4rem;
    line-height: 2.1rem;
  }

  .link {
    text-decoration: none;
    color: inherit;
  }

  .social-icons a:hover {
    background-color: #add8e6;
  }
</style>

<section
  class="resume-section p-3 p-lg-5 d-flex justify-content-center"
  use:observe
  id="projects">
  <div class="w-100">
    <h2 class="mb-3">Ongoing Projects</h2>

    {#each projects as project}
      <div
        class="resume-item d-flex flex-column flex-md-row
        justify-content-between mb-3">
        <div class="resume-content">
          <h4 class="mb-0">
            <span class="social-icons">
              <a href={project.source}>
                <i class="fab fa-github" />
              </a>
            </span>
            {project.name}
          </h4>
          <p>{project.description}</p>
        </div>
      </div>
    {/each}

  </div>
</section>
