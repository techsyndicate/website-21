<script>
  export let member, role, image, socials;
</script>

<div class="card">
  <img src={image} alt={member} />
  <div style="margin-left: 1vw;">
    <h3>{member}</h3>
    <p>{role}</p>
  </div>

  {#if socials}
    <div class="socials">
      {#each Object.entries(socials) as [social, link]}
        <a href={link} alt={social} target="_blank"
          ><i class="{social === 'medium' ? 'fab' : 'fa'} fa-{social}" /></a
        >
      {/each}
    </div>
  {/if}
  <div style="height: {socials ? '4vh' : '2vh'}" />
</div>

<style>
  .card {
    display: flex;
    flex-direction: column;
    text-align: left;
    background-color: #111;
    border-radius: 4px;
    width: 14vw;
    margin-right: 2vw;
  }

  img {
    border-radius: 4px;
    margin: 0 1vw;
    margin-top: 2vh;
    margin-bottom: 2vh;
    box-shadow: 0 6px 8px #0c0c0c;
  }

  h3 {
    margin: 0;
    font-weight: 500;
    font-size: 2.4vh;
  }

  p {
    margin: 0;
    margin-top: 0.8vh;
    color: #aaa;
    margin-bottom: 1.8vh;
    font-weight: normal;
    font-size: 1.8vh;
  }

  .socials {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    max-width: max-content;
    margin-left: 1vw;
    margin-right: 7vw;
    color: rgba(102, 102, 102, 0.904);
    font-size: 2.4vh;
  }

  a {
    text-decoration: none;
    color: rgba(102, 102, 102, 0.904);
    margin-right: 0.5vw;
  }

  .socials a:hover {
    color: #fff;
  }
</style>
