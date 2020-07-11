<script>
  import { activeSection } from "../store.js";

  const thingsILike = ["JavaScript", "Linux", "Vim", "Web"];
  const thingsIAmDoing = [
    {
      position: "Student",
      place: "Otago Polytechnic",
    },
  ];
  const socialPlatforms = [
    {
      link: "https://www.linkedin.com/in/trent-nicholson-61046a191/",
      icon: "fa-linkedin-in",
    },
    {
      link: "https://github.com/NICHTJ3",
      icon: "fa-github",
    },
  ];

  let observer = new IntersectionObserver(onIntersect, {
    threshold: 0.5,
  });

  function onIntersect([section]) {
    if (section.isIntersecting) {
      activeSection.set("home");
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
  #home {
    background-image: url(/img/background.jpg);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
  }

  .social-icons a {
    display: inline-block;
    height: 3.5rem;
    width: 3.5rem;
    background-color: #495057;
    color: #fff !important;
    border-radius: 100%;
    text-align: center;
    font-size: 1.5rem;
    line-height: 3.5rem;
    margin-right: 1rem;
  }

  .social-icons a:last-child {
    margin-right: 0;
  }

  .social-icons a:hover {
    background-color: #add8e6;
  }

  .subheading {
    text-transform: uppercase;
    font-weight: 500;
    font-family: "Saira Extra Condensed", -apple-system, BlinkMacSystemFont,
      "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif,
      "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol",
      "Noto Color Emoji";
    font-size: 1.5rem;
    color: #b9b3a8;
  }
</style>

<section
  class="resume-section p-3 p-lg-5 d-flex align-items-center"
  id="home"
  use:observe>
  <div class="w-100">
    <h1 class="mb-0">
      Trent
      <span class="text-primary">Nicholson</span>
    </h1>
    <div class="subheading mb-3">
      <br />
      {#each thingsIAmDoing as thing}
        {thing.position} @ {thing.place}
        <br />
      {/each}
      {thingsILike.join(', ')}
    </div>
    <div class="social-icons">
      {#each socialPlatforms as socialPlatform}
        <a href={socialPlatform.link}>
          <i class={`fab ${socialPlatform.icon}`} />
        </a>
      {/each}
    </div>
  </div>
</section>
