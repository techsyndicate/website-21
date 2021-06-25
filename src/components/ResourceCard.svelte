<script>
    export let field, slug, icon;
</script>

<a href={slug} target="_blank"><div class="resource">
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
    font-weight: 400;
  }

  @keyframes titleHoverOn {
    from {
      opacity: 0;
      transform: translateY(100%);
    }

    to {
      opacity: 1;
    }
  }

  @keyframes iconHoverOn {
      from {
          transform: translateY(0%);
      }

      to {
          transform: translateY(-10%);
      }
  }

  @keyframes titleHoverOff {
    from {
      transform: translateY(0%);
    }

    to {
      opacity: 0;
      transform: translateY(100%);
    }
  }

  @keyframes iconHoverOff {
    from {
      transform: translateY(-10%);
    }

    to {
      transform: translateY(0%);
    }
  }

  .resource:hover {
      cursor: pointer;
  }

  .resource:hover h4 {
    animation-name: titleHoverOn;
    animation-duration: 500ms;
    animation-fill-mode: both;
  }

  .resource:hover img {
      animation-name: iconHoverOn;
      animation-duration: 500ms;
      animation-fill-mode: both;
  }

  .resource h4 {
    animation-name: titleHoverOff;
    animation-duration: 500ms;
    animation-fill-mode: both;
  }

  .resource img {
    animation-name: iconHoverOff;
    animation-duration: 500ms;
    animation-fill-mode: both;
  }

  @media screen and (max-width: 768px) {
    .resource {
      max-width: 64vw;
      margin-bottom: 4vh;
      padding: 6.5vh 0;
    }

    .resource img {
      display: block;
      margin: 0 auto;
      width: 24vh;
    }

    .resource h4 {
      opacity: 1;
      display: block;
    }

    * {
      transition: none !important;
      animation-name: none !important;
    }
  }
</style>
