<script>
  let shorterText = false
  const screenWidth = screen.width
  if(screenWidth < 768) {
    shorterText = true
  }
  window.addEventListener("resize", () => {
    const screenWidth = screen.width
    if(screenWidth < 768) {
      shorterText = true
    } else {
      shorterText = false
    }
  })
</script>

<body>
  <footer class="footer">
    <div class="links">
      <a href="https://facebook.com/syndicateofamity46" target="_blank">
        <div class="link">
          <i class="fa fa-facebook-square"/>
        </div>
      </a>
      <a href="https://instagram.com/techsyndicate46" target="_blank">
        <div class="link">
          <i class="fa fa-instagram"/>
        </div>
      </a>
      <a href="mailto:contact@techsyndicate.club">
        <div class="link">
          <i class="fa fa-envelope"/>
        </div>
      </a>
      <a href="https://github.com/techsyndicate" target="_blank">
        <div class="link" style="margin-right: 0vw;">
          <i class="fa fa-github"/>
        </div>
      </a>
    </div>
    <div class="cr">
      <p>{shorterText ? 'Tech Syndicate · AISG-46' : 'Tech Syndicate · Amity International School, Sector 46, Gurgaon'}</p>
    </div>
  </footer>
</body>

<style>
  .footer {
    padding: 3vh 0;
    background-color: #111;
    width: 100vw;
    height: max-content;
  }

  a {
    text-decoration: none;
    color: #111;
  }

  .links {
    margin: auto;
    display: flex;
    justify-content: space-between;
    flex-flow: row wrap;
    align-items: center;
    width: fit-content;
    height: max-content;
  }

  .link {
    background-color: #fff;
    border-radius: 50%;
    text-align: center;
    margin-right: 1.4vw;
    height: 2.6vw;
    width: 2.6vw;
  }

  .link:hover {
    background-color: #16e16e;
    cursor: pointer;
  }

  .link i {
    line-height: 2.6vw;
    font-size: 1.2vw;
    color: #111;
  }

  footer .cr {
    text-align: center;
    font-weight: 600;
    margin-top: 2.5vh;
    font-size: 1vw;
  }

  footer p {
    color: rgba(102, 102, 102, 0.904);
    display: block;
    margin: 0 auto;
    text-align: center;
    font-weight: 500;
  }

  @media screen and (max-width: 768px) {
    .footer {
      height: 12vh;
    }

    .links {
      height: 3vh;
    }

    .link {
      height: 10vw;
      width: 10vw;
      margin-right: 5vw;
    }

    .link i {
      line-height: 10vw;
      font-size: 4vw;
      color: #111;
    }

    footer .cr {
      text-align: center;
      margin-top: 6vh;
      font-size: 3.2vw;
      padding: 0 3vw;
    }
  }
</style>
