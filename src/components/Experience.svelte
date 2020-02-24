<script>
  import { ScrollableSection } from "@beyonk/svelte-scrollspy";
  const experiences = [
    {
      position: "Software tester / Intern",
      company: "Abacus Bio",
      dateFrom: "dec 2019",
      dateEnd: "febuary 2020"
    }
  ];
</script>

<style>

</style>

<ScrollableSection id="experience">
  <section
    class="resume-section p-3 p-lg-5 d-flex justify-content-center"
    id="experience">
    <div class="w-100">
      <h2 class="mb-3">Experience</h2>

      {#each experiences as experience}
        <div
          class="resume-item d-flex flex-column flex-md-row
          justify-content-between mb-3">
          <div class="resume-content">
            <h4 class="mb-0">{experience.position} · {experience.company}</h4>
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
</ScrollableSection>
