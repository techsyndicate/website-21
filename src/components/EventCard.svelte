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
        max-width: 16vw;
        z-index: 2;
        overflow: hidden;
    }

    .bottom-items {
        display: flex;
        justify-content: space-between;
        min-height: 2vh;
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
        margin-bottom: -4vh;
    }

    p {
        font-size: 2vh;
    }
</style>