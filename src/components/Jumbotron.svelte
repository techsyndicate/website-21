<script>
  export let title, description;
</script>

<div class="jumbotron">
  <h1>{title}</h1>
  <p>{description}</p>
</div>

<style>
  h1 {
    color: #16e16e;
    font-size: 2.8vw;
  }

  p {
    color: #f3f3f3;
    margin-right: 15vw;
    font-size: 1.2vw;
  }

  @media screen and (max-width: 768px) {
      h1 {
          font-size: 4vh;
      }

      p {
          font-size: 2vh;
          margin-right: 0;
      }
  }
</style>
