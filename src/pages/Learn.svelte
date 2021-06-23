<script>
    import Jumbotron from "../components/Jumbotron.svelte";
    import EventCard from "../components/EventCard.svelte";
  
    import events from "../../data/events.json";
  </script>
  
  <body>
    <Jumbotron
      title="Learn"
      description="The learning resources have been compiled by the members of Tech Syndicate themselves and provide a strong understanding about the respective fields and about the skills required to excel in those fields."
    />
    <div style="height: 5vh" />
    <div style="height: 10vh" />
</body>

<style>
  body {
    padding: 0 18%;
  }
</style>