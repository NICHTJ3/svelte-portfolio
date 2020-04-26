<script>
  import { activeSection } from "../store.js";

  const navlinks = [
    { displayName: "Home", href: "#home", id: "home" },
    { displayName: "Experience", href: "#experience", id: "experience" },
    { displayName: "Awards and Education ", href: "#awards", id: "awards" },
    { displayName: "Ongoing projects", href: "#projects", id: "projects" }
  ];

  const name = "Trent Nicholson";
</script>

<style>
  #sideNav .navbar-nav .nav-item .nav-link {
    font-weight: 800;
    letter-spacing: 0.05rem;
    text-transform: uppercase;
  }

  #sideNav .navbar-toggler:focus {
    outline-color: #e8f4f8;
  }

  .active {
    color: #72bcd4;
  }

  @media (min-width: 992px) {
    #sideNav {
      text-align: center;
      position: fixed;
      top: 0;
      left: 0;
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-orient: vertical;
      -webkit-box-direction: normal;
      -ms-flex-direction: column;
      flex-direction: column;
      width: 17rem;
      height: 100vh;
    }

    #sideNav .navbar-brand {
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      margin: auto auto 0;
      padding: 0.5rem;
    }

    #sideNav .navbar-brand .img-profile {
      max-width: 10rem;
      max-height: 10rem;
      border: 0.5rem solid rgba(255, 255, 255, 0.2);
    }

    #sideNav .navbar-collapse {
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-align: start;
      -ms-flex-align: start;
      align-items: flex-start;
      -webkit-box-flex: 0;
      -ms-flex-positive: 0;
      flex-grow: 0;
      width: 100%;
      margin-bottom: auto;
    }

    #sideNav .navbar-collapse .navbar-nav {
      -webkit-box-orient: vertical;
      -webkit-box-direction: normal;
      -ms-flex-direction: column;
      flex-direction: column;
      width: 100%;
    }

    #sideNav .navbar-collapse .navbar-nav .nav-item {
      display: block;
    }

    #sideNav .navbar-collapse .navbar-nav .nav-item .nav-link {
      display: block;
    }
  }

  a {
    color: #add8e6;
  }

  .bg-primary {
    background-color: #17404d !important;
  }

  a:hover,
  a:focus,
  a:active {
    color: #17404d;
  }
</style>

<nav
  class="navbar navbar-expand-lg navbar-dark bg-primary fixed-top"
  id="sideNav">
  <a class="navbar-brand" href="#page-top">
    <span class="d-block d-lg-none">{name}</span>
    <span class="d-none d-lg-block">
      <img
        class="img-fluid img-profile rounded-circle mx-auto mb-2"
        src="https://avatars3.githubusercontent.com/u/39316919?s=400&u=02f9c31e01ffd14ec0dec546876a99c53f6ef4a9&v=4"
        alt="" />
    </span>
  </a>
  <button
    class="navbar-toggler"
    type="button"
    data-toggle="collapse"
    data-target="#navbarSupportedContent"
    aria-controls="navbarSupportedContent"
    aria-expanded="false"
    aria-label="Toggle navigation">
    <span class="navbar-toggler-icon" />
  </button>
  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav">
      {#each navlinks as navItem}
        <li class="nav-item">
          <a
            class:active={$activeSection == navItem.id}
            class="nav-link"
            href={navItem.href}>
            {navItem.displayName}
          </a>
        </li>
      {/each}
    </ul>
  </div>
</nav>
