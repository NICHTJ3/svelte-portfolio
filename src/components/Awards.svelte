<script>
  import { ScrollableSection } from "@beyonk/svelte-scrollspy";
  const awards = [
    {
      name: "Certificate in IT level 3 & 4",
      description: "[description here]",
      awarded: "[date awarded here]"
    }
  ];
</script>

<style>

</style>

<ScrollableSection id="awards">
  <section
    class="resume-section p-3 p-lg-5 d-flex justify-content-center"
    id="awards">
    <div class="w-100">
      <h2 class="mb-3">Awards</h2>

      {#each awards as award}
        <div
          class="resume-item d-flex flex-column flex-md-row
          justify-content-between mb-3">
          <div class="resume-content">
            <h4 class="mb-0">
              <i class="fa fa-trophy text-warning" />
              {award.name}
            </h4>
            <ul class="list-inline dev-icons" />
            {#if award.description}
              <p>award.description</p>
            {/if}
          </div>
          <div class="resume-date">
            <span class="text-primary">{award.awarded}</span>
          </div>
        </div>
      {/each}

    </div>
  </section>
</ScrollableSection>
