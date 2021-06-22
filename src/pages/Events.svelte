<script>
  import Jumbotron from "../components/Jumbotron.svelte";
  import EventCard from "../components/EventCard.svelte";

  import events from "../../data/events.json";
</script>

<body>
  <Jumbotron
    title="Events"
    description="Robotronics '21 comprises of 10 events, spanned across grades 3-12. There will be one overall prize, competing for which will require proficiency across a wide variety of fields."
  />

  <div style="height: 5vh" />

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

  <div style="height: 10vh" />
</body>

<style>
  body {
    padding: 0 18%;
  }
</style>