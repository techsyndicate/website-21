<script>
    export let field, url, icon;
</script>

<a href={url}><div class="resource">
  <img src={icon} alt={field} />
  <h4>{field}</h4>
</div></a>

<style>
  a {
      text-decoration: none;
      color: #fff;
  }
  .resource {
    border-radius: 10px;
    padding: 6vh 0;
    background: #1a1a1b;
    max-width: 20vw;
    max-height: 18vh;
    text-align: center;
  }

  img {
    display: block;
    margin: 0;
    width: 18vw;
    height: 18vh;
  }

  h4 {
    margin: 1vh 0;
    opacity: 0;
    font-weight: 300;
  }

  @keyframes title {
    from {
      opacity: 0;
      transform: translateY(100%);
    }

    to {
      opacity: 1;
    }
  }

  @keyframes icon {
      from {
          transform: translateY(0%);
      }

      to {
          transform: translateY(-10%);
      }
  }

  .resource:hover {
      cursor: pointer;
  }

  .resource:hover h4 {
    animation-name: title;
    animation-duration: 500ms;
    animation-fill-mode: both;
  }

  .resource:hover img {
      animation-name: icon;
      animation-duration: 500ms;
      animation-fill-mode: both;
  }
</style>
