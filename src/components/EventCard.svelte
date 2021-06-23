<script>
  export let event, description, eligibility, participants, format, icon, color;
</script>

<div class="card" style="background: {color};">
  <h3>{event}</h3>

  <p>Eligibility: {eligibility}<br />Participants: {participants}</p>
  <p>{description}</p>

  <div class="bottom-items">
    <a href={format}><button type="button" class="card-button" style="color: {color};">Prelims&nbsp;&gt;</button></a>
    <img src={icon} alt="code"/>
  </div>
</div>

<style>
    .card {
        border-radius: 14px;
        padding: 1.5vh 1.5vw;
        padding-top: 0.1vh;
        max-width: 16vw;
        z-index: 2;
        overflow: hidden;
        position: relative;
    }

    .bottom-items {
        display: flex;
        justify-content: space-between;
        height: 20vh;
        /* background-color: antiquewhite; */
    }

    button {
        border-radius: 8px;
        border: none;
        padding: 1vh 1.5vw;
        background: #fff;
        font-weight: 600;
        margin-top: 100%;
    }

    img {
        width: 32vw;
        height: 32vh;
        margin-top: -5vh;
    }

    p {
        font-size: 2vh;
    }

    h3 {
      font-size: 3vh;
    }

    .card-button {
      position: absolute;
      bottom: 0;
      margin-bottom: 1.5vw;
      font-size: 1vw;
    }

    .bottom-items img {
      margin-left: 45%;
    }
</style>