<script>
  export let sectionId;
  export let center;
  import { activeSection } from "../store.js";

  let observer = new IntersectionObserver(onIntersect, {
    threshold: 0.5,
  });

  function onIntersect([section]) {
    if (section.isIntersecting) {
      activeSection.set(sectionId);
    }
  }

  function observe(node) {
    observer && observer.observe(node);
    return {
      destroy() {
        observer && observer.unobserve(node);
      },
    };
  }
</script>

<style>
  @media (min-width: 992px) {
    section.resume-section {
      padding-top: 3rem !important;
      padding-bottom: 3rem !important;
    }
  }
  section.resume-section {
    padding-top: 5rem !important;
    padding-bottom: 5rem !important;
    max-width: 75rem;
    min-height: 100vh;
  }
</style>

<section
  class="resume-section p-3 p-lg-5 d-flex"
  class:align-items-center={center}
  class:justify-content-center={!center}
  use:observe
  id={sectionId}>
  <div class="w-100">
    <slot />
  </div>
</section>
