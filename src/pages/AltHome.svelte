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
    <img src="/assets/images/illus-mob.png" alt="illus-mob" />
    <div class="text">
      <p>July 20 – July 30, 2021</p>
      <h1>ROBOTRONICS '21</h1>
      <div class="buttons">
        <a
          href="https://t11e.us/server"
          style="text-decoration: none;"
          target="_blank"><button class="nav-link-button">Discord</button></a
        >
        <a class="video-play-button" id="play">
          <span class="watch" id="watch-text">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="20.534"
              height="20.534"
              viewBox="0 0 29.534 29.534"
              style="margin-right: 1.5vw;"
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
    <p>
      Robotronics '21, the 8th edition of Tech Syndicate's annual event, will
      take place from 20th July to 30th July. Beginning as a robotics exclusive
      symposium, Robotronics has now evolved and branched out to include in
      events across a much wider variety of domains.
      <br />
      <br />
      Being shifted to an online medium, Robotronics has scaled up to become one
      of the most prominent tech symposiums in Delhi, with over 300+ students from
      35 schools and 40+ individual teams across Delhi NCR taking part in 2020.
      <br />
      <br />
      This year, there will be 11 events taking place for both juniors and seniors.
      There will be one school crowned as the overall winner after taking into consideration
      all the 11 events.
      <br /><br /><a href="https://t11e.us/eventguide" target="_blank"
        ><button class="section-button">Event Guide&nbsp;&nbsp;&gt; </button></a
      >
    </p>
    <img src="/assets/images/tscircuitglow.png" alt="tscircuitglow" />
  </div>
  <div class="third-section">
    <h1>Tech Syndicate</h1>
    <p>
      Established in 2016, Tech Syndicate is the technology club of Amity
      International School, Sector-46, Gurgaon. The club works constantly to
      encourage students to learn new technologies and keep up with the rapidly
      progressing sector of computer science.
      <br />
      <br />
      Through the years, it has transformed into a family of designers, developers,
      programmers, and filmmakers who dominate their fields. The members of the club
      have won several inter-school, national and international events, and have
      repeatedly brought accolades to the school.
      <br /><br />
      <Link to="members"
        ><button class="section-button">Members&nbsp;&nbsp;&gt;</button></Link
      >
    </p>
    <img src="/assets/images/tsis.png" alt="tscircuitglow" style="margin-bottom: 13vh;"/>
  </div>
</body>

<style>
  .first-section {
    height: 105vh;
    width: 100vw;
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    background-color: rgb(2, 2, 2);
    margin-top: -2.5vh;
  }

  .first-section img {
    height: auto;
    width: 100vw;
    margin-left: 0vw;
    margin-top: -20vh;
    opacity: 0.7;
  }

  .first-section .text {
    width: 90vw;
    height: 10vh;
    background-color: transparent !important;
    position: absolute;
    bottom: 0;
    margin-bottom: 15vh;
    margin-left: 5vw;
  }

  .text h1 {
    font-size: 10vw;
    outline: none;
    margin-top: -2vw;
  }

  .text p {
    font-size: 4.5vw;
  }

  .buttons {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    margin-left: 0vw;
    margin-top: -4vw;
  }

  .watch {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    color: #16e16e;
    font-size: 3.5vw;
    margin-left: 3vw;
  }

  .nav-link-button {
    height: 8vw;
    width: 20vw;
    border: none;
    text-align: center;
    padding-left: 1vw;
    padding-right: 1vw;
    color: white;
    background-color: #00af3b;
    font-size: 3.5vw;
    border-radius: 5px;
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
    font-size: 3.5vw;
    margin-left: 0;
    padding: 1vh 2vw;
    transition: all 0.2s ease-out;
    display: inline-block;
    margin-bottom: 2vh;
  }

  .section-button:hover {
    transform: translateX(0.5vh);
    cursor: pointer;
  }

  .video-play-button {
    text-decoration: none;
    margin-top: -0.5vw;
  }

  .video-play-button:hover {
    cursor: pointer;
  }

  .second-section {
    height: fit-content;
    width: 85vw;
    margin-top: -10vh;
    padding-left: 7vw;
    padding-right: 10vw;
    background-color: #111;
    padding-top: 3vh;
    padding-bottom: 3vh;
  }

  .second-section img {
    height: auto;
    width: 90vw;
    margin-left: -2vw;
    margin-top: 3vh;
  }

  .third-section {
    height: fit-content;
    width: 85vw;
    margin-top: 0vh;
    padding-left: 7vw;
    padding-right: 10vw;
    padding-top: 3vh;
  }

  .third-section h1 {
    font-size: 8vw;
    color: #16e16e;
  }

  .third-section img {
    height: auto;
    width: 90vw;
    margin-left: -2vw;
    margin-top: 0vh;
  }
</style>
