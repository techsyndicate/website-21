<script>
    import Jumbotron from "../components/Jumbotron.svelte";
    import MemberCard from "../components/MemberCard.svelte";
    import SearchBar from "../components/SearchBar.svelte";
    import members from "../../data/members.json";
  </script>
  
  <body>
    <Jumbotron
      title="Alumni"
      description="Tech Syndicate has a vast and diverse alumni network mapped all over the globe that has been a mentor for the club's members and have shaped the club into what it is today."
    />
    <div style="height: 3vh" />
    <SearchBar />
    <div style="height: 10vh" />
  
    <!-- {#each members as rows}
      <div style="display: flex; justify-content: space-between;">
        {#each rows as member}
          <MemberCard
            member={member.name}
            role={member.role}
            image={member.image}
            website={member.website}
          />
        {/each}
      </div>
      <div style="height: 8vh" />
    {/each} -->
  
    <div style="height: 10vh" />
  </body>
  
  <style>
    body {
      padding: 0 18%;
    }
  </style>