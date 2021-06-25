<svelte:head>
  <title>TS | Events</title>
</svelte:head>

<script>
  import Jumbotron from "../components/Jumbotron.svelte";
  import EventCard from "../components/EventCard.svelte";

  import events from "../../data/events.json";
</script>

<body>
  <Jumbotron
    title="Events"
    description="Robotronics 2021 comprises of 11 events, spanned across grades 3-12. There will be one overall prize, competing for which will require proficiency across a wide variety of fields."
  />

  <div style="height: 5vh" />

  {#each events as rows}
    <div class="container">
      {#each rows as event}
        <EventCard
          event={event.name}
          eligibility={event.eligibility}
          participants={event.participants}
          description={event.description}
          icon={event.icon}
          color={event.color}
          format={event.format}
          buttonText={event.buttonText}
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
    justify-content: left;
  }

  .sized-box {
    height: 6vh;
  }

  @media screen and (max-width: 768px) {
    body {
      padding: 0 8%;
    }

    .container {
      display: block;
      justify-content: center;
    }

    .sized-box {
      height: 0;
    }
  }
</style>