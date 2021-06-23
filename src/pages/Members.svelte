<script>
    import Jumbotron from "../components/Jumbotron.svelte";
    import MemberCard from "../components/MemberCard.svelte";
    import SearchBar from "../components/SearchBar.svelte";
    import members from "../../data/members.json";
  </script>
  
  <body>
    <Jumbotron
      title="Members"
      description="Tech Syndicate's team comprises of members with a wide array of skills ranging all the way from hardware and quiz to web development and design, all united by the passion and enthusiasm for tech."
    />
    <div style="height: 3vh" />
    <SearchBar />
    <div style="height: 4vh" />
  
    {#each members as rows}
      <div style="display: flex; justify-content: space-between;">
        {#each rows as member}
          <MemberCard
            member={member.name}
            role={member.role}
            image={member.image}
            socials={member.socials}
          />
        {/each}
      </div>
      <div style="height: 4vh" />
    {/each}
  
    <div style="height: 10vh" />
  </body>
  
  <style>
    body {
      padding: 0 18%;
    }
  </style>