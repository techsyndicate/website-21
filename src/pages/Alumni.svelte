<script>
  import Jumbotron from "../components/Jumbotron.svelte";
  import MemberCard from "../components/MemberCard.svelte";
  import SearchBar from "../components/SearchBar.svelte";
  import alumni from "../../data/alumni.json";
</script>

<body>
  <Jumbotron
    title="Alumni"
    description="Tech Syndicate has a vast and diverse alumni network mapped all over the globe that has been a mentor for the club's members and have shaped the club into what it is today."
  />
  <div style="height: 3vh" />
  <SearchBar />
  <div style="height: 4vh" />

  {#each alumni as batch}
    <h2>{batch.batch}</h2>
    {#each batch.alumni as row}
      <div style="display: flex; justify-content: space-between; max-width: max-content;">
        {#each row as alum}
          <MemberCard
            member={alum.name}
            role={alum.exrole}
            image={alum.image}
          />
        {/each}
      </div>
      <div style="height: 4vh;" />
    {/each}
  {/each}

  <div style="height: 10vh" />
</body>

<style>
  body {
    padding: 0 18%;
  }
</style>
