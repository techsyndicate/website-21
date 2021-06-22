<script>
  import Jumbotron from "../components/Jumbotron.svelte";
  import EventCard from "../components/EventCard.svelte";

  import events from "../../data/events.json";
</script>

<body>
  <Jumbotron
    title="Events"
    description="Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book."
  />

  <div style="height: 2vh" />

  {#each events as rows}
    <div style="display: flex; justify-content: space-between;">
      {#each rows as event}
        <EventCard
          event={event.name}
          eligibility={event.eligibility}
          participants={event.participants}
          description={event.description}
          icon={event.icon}
          color={event.color}
          format={event.format}
        />
      {/each}
    </div>
    <div style="height: 8vh" />
  {/each}

  <div style="height: 2vh" />
</body>

<style>
  body {
    padding: 0 18%;
  }
</style>