<script>
  export let event, description, eligibility, participants, format, icon, color, buttonText;
</script>

<div class="card" style="background: {color};">
  <h3>{event}</h3>

  <p>Eligibility: {eligibility}<br />Participants: {participants}</p>
  <p>{description}</p>

  <div class="bottom-items">
    <a href="{format}" target="_blank"><button type="button" class="card-button" style="color: {color};">{buttonText}&nbsp;&gt;</button></a>
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
        margin-right: 2vw;
    }

    .bottom-items {
        display: flex;
        justify-content: space-between;
        height: 20vh;
    }

    button {
        border-radius: 8px;
        border: none;
        padding: 1vh 1.5vw;
        background: #fff;
        font-weight: 600;
        margin-top: 100%;
    }

    button:hover {
      cursor: pointer;
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
      transition: all 0.2s ease-out;
      display: inline-block;
      z-index: 2;
    }

    .card-button:hover {
      transform: translateX(0.5vh);
    }

    .bottom-items img {
      position: absolute;
      bottom: 0;
      left: 0;
      margin-bottom: -2.5vw;
      z-index: 0;
    }

    @media screen and (max-width: 768px) {
      .card {
        width: 100%;
        margin: 0;
        max-width: 72vw;
        max-width: 72vw;
        padding: 4vh 6vw;
        margin-bottom: 4vh;
      }

      h3 {
        margin: 0;
      }

      .bottom-items {
        padding-bottom: 1vh;
      }

      button {
        padding: 1vh 2vw;
      }

      .card-button {
        font-size: 2vh;
        margin-bottom: 3vh;
      }

      img {
        width: 54vw;
        height: 54vh;
        margin-top: -12vh;
        margin-right: -18vw;
        margin-bottom: 4vh;
      }

      .bottom-items img {
        margin-bottom: -30vw;
        margin-left: 42vw;
      }
    }
</style>