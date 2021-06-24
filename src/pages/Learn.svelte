<svelte:head>
  <title>TS | Learn</title>
</svelte:head>

<script>
  import Jumbotron from "../components/Jumbotron.svelte";
  import ResourceCard from "../components/ResourceCard.svelte";

  import resources from "../../data/resources.json";
</script>

<body>
  <Jumbotron
    title="Learn"
    description="The learning resources have been compiled by the members of Tech Syndicate themselves and provide a strong understanding about the respective fields and about the skills required to excel in those fields."
  />
  <div style="height: 5vh" />

  {#each resources as rows}
    <div style="display: flex; justify-content: space-between;">
      {#each rows as resource}
        <ResourceCard
          field={resource.name}
          icon={resource.icon}
          slug={resource.slug}
        />
      {/each}
    </div>
    <div style="height: 8vh" />
  {/each}
  <div style="height: 10vh" />
</body>

<style>
  body {
    padding: 0 18%;
  }
</style>
