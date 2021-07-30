<script>
  import { Link } from "svelte-navigator";
  let activePath = window.location.pathname;
  let resp = false
  let showSidebar = false
  let showNav = true

  const screenWidth = screen.width;
  if (screenWidth < 768) {
    resp = true
  } else {
    resp = false
  }

  window.addEventListener("resize", () => {
    const screenWidth = screen.width;
    if (screenWidth < 768) {
      resp = true
    } else {
      resp = false
    }
  });

  window.addEventListener("click", (e) => {
    activePath = window.location.pathname;
    if (e.target.id === "hamburger-icon") {
      showSidebar = true
      showNav = false
    } else if (e.target.id === "close-icon" || "sidebar-link" || e.target.id === "ts-sidebar") {
      showSidebar = false
      showNav = true
    }
  });
</script>

<body>
  {#if showNav === true}
      {#if resp === true}
      <nav>
        <div class="left">
          {#if activePath !== "/"}
            <Link to="/"><img src="/assets/images/ts.png" alt="ts" id="ts" /></Link>
          {:else}
            <Link to="/"><img src="/assets/images/ts.png" alt="ts" id="ts" style="margin-top: -1vw;" /></Link>
          {/if}
        </div>
        <div class="right">
          {#if activePath !== "/"}
            <img
              src="/assets/icons/hamburger.svg"
              alt="hamburger-icon"
              id="hamburger-icon"
            />
          {:else}
            <img
              src="/assets/icons/hamburger.svg"
              alt="hamburger-icon"
              id="hamburger-icon"
              style="margin-top: -1vw;"
            />
          {/if}
        </div>
      </nav>
    {:else}
      <nav>
        <div class="left">
          <Link to="/"><img src="/assets/images/ts.png" alt="ts" /></Link>
        </div>
        <div class="right">
          {#if activePath === "/events"}
            <Link to="/events" style="text-decoration: none;"
              ><span class="nav-link active">Events</span></Link
            >
          {:else}
            <Link to="/events" style="text-decoration: none;"
              ><span class="nav-link">Events</span></Link
            >
          {/if}
          {#if activePath === "/members"}
            <Link to="/members" style="text-decoration: none;"
              ><span class="nav-link active">Members</span></Link
            >
          {:else}
            <Link to="/members" style="text-decoration: none;"
              ><span class="nav-link">Members</span></Link
            >
          {/if}
          {#if activePath === "/alumni"}
            <Link to="/alumni" style="text-decoration: none;"
              ><span class="nav-link active">Alumni</span></Link
            >
          {:else}
            <Link to="/alumni" style="text-decoration: none;"
              ><span class="nav-link">Alumni</span></Link
            >
          {/if}
          {#if activePath === "/learn"}
            <Link to="/learn" style="text-decoration: none;"
              ><span class="nav-link active">Learn</span></Link
            >
          {:else}
            <Link to="/learn" style="text-decoration: none;"
              ><span class="nav-link">Learn</span></Link
            >
          {/if}
        </div>
      </nav>
    {/if}
  {/if}
  {#if showSidebar === true}
    <div class="sidebar">
      <img src="/assets/icons/close.svg" alt="close" id="close-icon" />
      <div class="links">
        <Link to="/"
          ><img src="/assets/images/ts.png" alt="ts" id="ts-sidebar" /></Link
        >
        {#if activePath === "/events"}
          <Link to="/events" style="text-decoration: none;"
            ><p
              class="sidebar-nav-link sidebar-nav-link-active"
              id="sidebar-link"
            >
              Events
            </p></Link
          >
        {:else}
          <Link to="/events" style="text-decoration: none;"
            ><p class="sidebar-nav-link" id="sidebar-link">Events</p></Link
          >
        {/if}
        {#if activePath === "/members"}
          <Link to="/members" style="text-decoration: none;"
            ><p
              class="sidebar-nav-link sidebar-nav-link-active"
              id="sidebar-link"
            >
              Members
            </p></Link
          >
        {:else}
          <Link to="/members" style="text-decoration: none;"
            ><p class="sidebar-nav-link" id="sidebar-link">Members</p></Link
          >
        {/if}
        {#if activePath === "/alumni"}
          <Link to="/alumni" style="text-decoration: none;"
            ><p
              class="sidebar-nav-link sidebar-nav-link-active"
              id="sidebar-link"
            >
              Alumni
            </p></Link
          >
        {:else}
          <Link to="/alumni" style="text-decoration: none;"
            ><p class="sidebar-nav-link" id="sidebar-link">Alumni</p></Link
          >
        {/if}
        {#if activePath === "/learn"}
          <Link to="/learn" style="text-decoration: none;"
            ><p
              class="sidebar-nav-link sidebar-nav-link-active"
              id="sidebar-link"
            >
              Learn
            </p></Link
          >
        {:else}
          <Link to="/learn" style="text-decoration: none;"
            ><p class="sidebar-nav-link" id="sidebar-link">Learn</p></Link
          >
        {/if}
      </div>
    </div>
  {/if}
</body>

<style>
  nav {
    padding-left: 5vw;
    padding-right: 5vw;
    padding-top: 2vh;
    padding-bottom: 2vh;
    background-color: transparent;
    width: 90vw;
    height: 5.5vh;
    display: flex;
    flex-flow: row wrap;
    align-items: center;
  }

  nav img {
    width: 3vw;
    height: 3vw;
    /* margin-top: -0.5vh; */
  }

  nav .right {
    position: absolute;
    right: 0;
    margin-right: 5vw;
    display: flex;
    flex-flow: row wrap;
    align-items: center;
  }

  .nav-link {
    font-size: 0.98vw;
    color: white;
    text-decoration: none;
    transition: all 0.3s;
    /* width: 10vw; */
    margin-left: 4vw;
    position: relative;
  }

  .nav-link::after {
    content: "";
    position: absolute;
    bottom: -2px;
    left: 0;
    width: 0;
    height: 2px;
    background: #16e16e;
    transition: all 0.2s;
  }

  .nav-link:hover:after {
    width: 100%;
  }

  .active:after {
    width: 100%;
  }

  .nav-link-button {
    text-decoration: none;
    border: 1px solid #00ae40;
    background-color: #00ae40;
    color: #fff;
    border-radius: 5px;
    font-size: 1vw;
    margin-left: 4vw;
    padding: 0.8vh 1.8vw;
    transition: all 0.2s ease-out;
    display: inline-block;
    }

  .nav-link-button:hover {
    transform: translateY(-0.5vh);
  }

  .sidebar {
    background-color: #111;
    width: 100vw;
    height: 200vw;
    z-index: 9999999;
    overflow: hidden;
    overflow-y: hidden;
    position: fixed;
  }

  .sidebar img {
    position: absolute;
    right: 0;
    margin-right: 10.5vw;
    width: 4.5vw;
    height: 4.5vw;
    margin-top: 8vw;
  }

  .sidebar .links {
    height: 100%;
    width: 100vw;
    margin: auto;
    text-align: center;
    padding-top: 32vh;
  }

  #ts-sidebar {
    width: 18vw;
    height: 18vw;
    margin-right: 42.5%;
    margin-top: -20vw;
  }

  .sidebar-nav-link {
    font-size: 5vw;
    margin-top: 7vw;
    color: white;
  }

  .sidebar-nav-link-button {
    border: none;
    background-color: #00af3b;
    color: white;
    border-radius: 5px;
    font-size: 5vw;
    padding: 1vh 3vw;
    margin-top: 3vw;
  }

  .sidebar-nav-link-active {
    color: #16e16e;
  }

  @media screen and (max-width: 768px) {
    nav img {
      width: 10vw;
      height: 10vw;
      margin-top: 3vw;
      margin-right: 3vw;
      /* margin-top: -0.5vh; */
    }

    #ts {
      width: 12vw;
      height: 12vw;
      margin-top: 1vw;
    }
  }
</style>
