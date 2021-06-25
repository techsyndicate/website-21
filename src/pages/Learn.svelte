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
    <div class="container">
      {#each rows as resource}
        <ResourceCard
          field={resource.name}
          icon={resource.icon}
          slug={resource.slug}
        />
      {/each}
    </div>
    <div class="sized-box" />
  {/each}
  <div style="height: 10vh" />
</body>

<style>
  body {
    padding: 0 18%;
  }

  .container {
    display: flex;
    justify-content: space-between;
  }

  .sized-box {
    height: 8vh;
  }

  @media screen and (max-width: 768px) {
    body {
      padding: 0 8%;
    }

    .container {
      margin: 0;
      display: block;
      justify-content: left;
    }

    .sized-box {
      height: 0;
    }
  }
</style>
