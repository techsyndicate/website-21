<script>
  import BigPicture from "bigpicture";
  import { Link } from "svelte-navigator";

  window.addEventListener("click", (e) => {
    if (e.target.id === "watch-icon" || e.target.id === "watch-text") {
      BigPicture({
        el: e.target,
        ytSrc: "erE1Nf2hCmk",
        dimensions: [960, 540],
      });
    }
  });
</script>

<svelte:head>
  <title>TS | Home</title>
</svelte:head>

<body>
  <div class="first-section">
    <div>
      <img src="/assets/images/illus-bg-2.png" alt="illus-bg" />
    </div>
    <div class="text">
      <h1>ROBOTRONICS '21</h1>
      <p>July 20 – July 30, 2021</p>
      <div class="buttons">
        <a
          href="https://t11e.us/server"
          style="text-decoration: none;"
          target="_blank"><span class="nav-link-button">Discord</span></a
        >
        <a class="video-play-button" id="play">
          <span class="watch" id="watch-text">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="24.534"
              height="24.534"
              viewBox="0 0 29.534 29.534"
              style="margin-right: 0.5vw;"
              id="watch-icon"
            >
              <path
                id="Icon_material-play-circle-outline"
                data-name="Icon material-play-circle-outline"
                d="M14.814,24.412l8.86-6.645-8.86-6.645ZM17.767,3A14.767,14.767,0,1,0,32.534,17.767,14.773,14.773,0,0,0,17.767,3Zm0,26.581A11.814,11.814,0,1,1,29.581,17.767,11.829,11.829,0,0,1,17.767,29.581Z"
                transform="translate(-3 -3)"
                fill="#00af3b"
              />
            </svg>
            Watch
          </span>
        </a>
      </div>
    </div>
  </div>
  <div class="second-section">
    <div class="left">
      <h1><span style="color: #16e16e">Robotronics</span> '21</h1>
      <p>
        Robotronics '21, the 8th edition of Tech Syndicate's annual event, will
        take place from July 20, 2021 to July 30, 2021. Beginning as a robotics
        exclusive symposium, Robotronics has now evolved and branched out to
        include events across a much wider variety of domains.
        <br />
        <br />
        Being shifted to an online medium, Robotronics has scaled up to become one
        of the most prominent tech symposiums in Delhi, with over 300+ students from
        35 schools and 40+ individual teams across Delhi NCR taking part in 2020.
        <br />
        <br />
        This year, there will be 11 events taking place for both juniors and seniors.
        There will be one school crowned as the overall winner after taking into
        consideration all the 11 events.
        <br /><br /><a href="https://t11e.us/eventguide" target="_blank"
          ><button class="section-button"
            >Event Guide&nbsp;&nbsp;&gt;
          </button></a
        >
      </p>
    </div>
    <div class="right">
      <img src="/assets/images/tscircuitglow.png" alt="ts-illus-2-glow" />
    </div>
  </div>
  <div class="third-section">
    <div class="left">
      <img src="/assets/images/tsis.png" alt="ts-illus-2" />
    </div>
    <div class="right">
      <h1 style="color: #16e16e;">Tech Syndicate</h1>
      <p>
        Established in 2016, Tech Syndicate is the technology club of Amity
        International School, Sector-46, Gurgaon. The club works constantly to
        encourage students to learn new technologies and keep up with the
        rapidly progressing sector of computer science.
        <br />
        <br />
        Through the years, it has transformed into a family of designers, developers,
        programmers, and filmmakers who dominate their fields. The members of the
        club have won several inter-school, national and international events, and
        have repeatedly brought accolades to the school.
        <br/><br/><Link to="members"
        ><button class="section-button"
          >Members&nbsp;&nbsp;&gt;
        </button></Link
      >
      </p>
    </div>
  </div>
</body>

<style>
  .first-section {
    height: 100vh;
    width: 100vw;
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    background-color: #010101;
  }

  .first-section img {
    height: auto;
    width: 100vw;
    margin-left: 5vw;
    margin-top: -25vh;
    opacity: 0.72;
  }

  .first-section .text {
    width: 30vw;
    height: 10vh;
    background-color: transparent;
    position: absolute;
    top: 0;
    margin-top: 35vh;
    margin-left: 5vw;
  }

  .text h1 {
    font-size: 3vw;
    outline: none;
  }

  .text p {
    font-size: 1.2vw;
    margin-top: -3vh;
  }

  .buttons {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    margin-left: -4vw;
    margin-top: 1vw;
  }

  .watch {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    color: #16e16e;
    font-size: 1vw;
    margin-left: 1vw;
  }

  .nav-link-button {
    text-decoration: none;
    border: 1px solid #00ae40;
    background-color: #00ae40;
    color: #fff;
    border-radius: 5px;
    font-size: 1vw;
    margin-left: 4vw;
    padding: 0.8vh 1.8vw;
    transition: all 0.2s ease-out;
    display: inline-block;
  }

  .nav-link-button:hover {
    transform: translateY(-0.5vh);
  }

  .section-button {
    text-decoration: none;
    border: 1px solid #00ae40;
    background-color: #00ae40;
    color: #fff;
    border-radius: 5px;
    font-size: 1vw;
    margin-left: 0;
    padding: 0.8vh 1vw;
    transition: all 0.2s ease-out;
    display: inline-block;
  }

  .section-button:hover {
    transform: translateX(0.5vh);
    cursor: pointer;
  }

  .second-section {
    height: 75vh;
    width: 80vw;
    margin-top: 0;
    margin-bottom: 0;
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    padding-left: 5vw;
    padding-right: 5vw;
  }

  .second-section .left {
    width: 38vw;
    height: 55vh;
    position: absolute;
    left: 0;
    margin-left: 5vw;
  }

  .second-section .right {
    margin-left: 10%;
    width: 45%;
    height: 55vh;
    position: absolute;
    right: 0;
    margin-right: 5vw;
  }

  .second-section .right img {
    width: 100%;
    height: auto;
    margin-top: 3vh;
  }

  .video-play-button {
    text-decoration: none;
  }

  .video-play-button:hover {
    cursor: pointer;
  }

  .second-section .left h1 {
    font-size: 2.5vw;
  }

  .second-section .left p {
    font-size: 1.1vw;
  }

  .third-section {
    height: 75vh;
    width: 100vw;
    margin-top: 0;
    margin-bottom: 0;
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    padding-left: 5vw;
    padding-right: 5vw;
  }

  .third-section .left {
    width: 38vw;
    height: 55vh;
    position: absolute;
    left: 0;
    margin-left: 5vw;
  }

  .third-section .right {
    margin-left: 10%;
    width: 45%;
    height: 55vh;
    position: absolute;
    right: 0;
    margin-right: 5vw;
    margin-top: -13vh;
  }

  .third-section .left img {
    width: 100%;
    height: auto;
    margin-left: 0vw;
    margin-top: -4vh;
  }

  .third-section .right h1 {
    font-size: 2.5vw;
  }

  .third-section .right p {
    font-size: 1.1vw;
  }
</style>
