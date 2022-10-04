<script>
  import Section from "../components/Section.svelte";

  const awards = [
    {
      name: "Bachelor of information technology with Distinction",
      awarded: "June 2020",
    },
    {
      name: "Excellence in Bachelor of information technology",
      awarded: "2019 and 2020",
    },
    {
      name: "Certificate in IT level 3 & 4",
      awarded: "November 2016, June 2017",
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
</style>

<Section sectionId="awards">
  <h2 class="mb-3">Awards and Education</h2>

  {#each awards as award}
    <div
      class="resume-item d-flex flex-column flex-md-row justify-content-between
      mb-3">
      <div class="resume-content">
        <h4 class="mb-0">
          <i class="fa fa-trophy text-warning" />
          {award.name}
        </h4>
        <br />
        {#if award.description}
          <p>award.description</p>
        {/if}
      </div>
      <div class="resume-date">
        <span class="text-primary">{award.awarded}</span>
      </div>
    </div>
  {/each}
</Section>
