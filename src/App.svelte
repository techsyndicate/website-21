<script>
  import { Router, Route, Link } from "svelte-navigator";
  import Navbar from "./components/Navbar.svelte";
  import Home from "./pages/Home.svelte";
  import AltHome from "./pages/AltHome.svelte";
  import Events from "./pages/Events.svelte";
  import Members from "./pages/Members.svelte";
  import Alumni from "./pages/Alumni.svelte";
  import Learn from "./pages/Learn.svelte";
  import Footer from "./components/Footer.svelte";
  import NotFound from "./pages/NotFound.svelte";

  let resp = false

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
</script>

<Router>
  <header>
    <Navbar />
  </header>
  <main>
    <Route path="/">
      {#if resp === true}
        <AltHome/>
      {:else}
        <Home/>
      {/if}
    </Route>
    <Route path="events">
      <Events />
    </Route>
    <Route path="members">
      <Members />
    </Route>
    <Route path="alumni">
      <Alumni />
    </Route>
    <Route path="learn">
      <Learn />
    </Route>
    <Route component={NotFound} />
  </main>
  <Footer />
</Router>
