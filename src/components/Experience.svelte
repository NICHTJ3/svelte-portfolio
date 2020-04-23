<script>
  import { activeSection } from "../store.js";

  const experiences = [
    {
      position: "Software tester / Intern",
      company: "Abacus Bio",
      url: "https://abacusbio.com/",
      dateFrom: "dec 2019",
      dateEnd: "febuary 2020"
    }
  ];

  let observer = new IntersectionObserver(onIntersect, {
    threshold: 0.8
  });

  function onIntersect([section]) {
    if (section.isIntersecting) {
      activeSection.set("experience");
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

</style>

<section
  class="resume-section p-3 p-lg-5 d-flex justify-content-center"
  use:observe
  id="experience">
  <div class="w-100">
    <h2 class="mb-3">Experience</h2>

    {#each experiences as experience}
      <div
        class="resume-item d-flex flex-column flex-md-row
        justify-content-between mb-3">
        <div class="resume-content">
          <h4 class="mb-0">
            {experience.position} ·
            <a class="text-primary" href={experience.url}>
              {experience.company}
            </a>
          </h4>
          <ul class="list-inline dev-icons" />
          <p />
        </div>
        <div class="resume-date">
          <span class="text-primary">
            {experience.dateFrom} - {experience.dateEnd}
          </span>
        </div>
      </div>
    {/each}

  </div>
</section>
