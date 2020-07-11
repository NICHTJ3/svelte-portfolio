<script>
  import Section from "../components/Section.svelte";

  const experiences = [
    {
      position: "Software tester / Intern",
      company: "Abacus Bio",
      url: "https://abacusbio.com/",
      dateFrom: "dec 2019",
      dateEnd: "febuary 2020",
    },
  ];
</script>

<style>
  @media (min-width: 768px) {
    section.resume-section .resume-item .resume-date {
      min-width: 18rem;
    }
  }
  section.resume-section .resume-item .resume-date {
    min-width: none;
  }

  a:hover,
  a:focus,
  a:active {
    text-decoration: none;
    color: inherit !important;
  }
</style>

<Section sectionId="experience">
  <h2 class="mb-3">Experience</h2>

  {#each experiences as experience}
    <div
      class="resume-item d-flex flex-column flex-md-row justify-content-between
      mb-3">
      <div class="resume-content">
        <h4 class="mb-0">
          {experience.position} ·
          <a class="text-primary link" href={experience.url}>
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

</Section>
