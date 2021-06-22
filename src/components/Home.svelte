
<header>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/fancyapps/fancybox@3.5.7/dist/jquery.fancybox.min.css" />
    <script src="https://cdn.jsdelivr.net/gh/fancyapps/fancybox@3.5.7/dist/jquery.fancybox.min.js"></script>
</header>

<style>
    .first-section {
        height: 100vh;
        width: 100vw;
        display: flex;
        flex-flow: row wrap;
        align-items: center;
    }

    .first-section img {
        height: auto;
        width: 90vw;
        margin-left: 35vh;
        /* margin-left: 25vw; */
        margin-top: -5vh;
        /* background-color: */
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
    }

    .text p {
        font-size: 1.2vw;
        margin-top: -3vh
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
        margin-left: 1.5vw;
    }

    .nav-link-button {
        text-decoration: none;
        border:none;
        background-color: #00AF3B;
        color: white;
        border-radius: 5px;
        font-size: 1vw;
        margin-left: 4vw;
        padding: 0.8vh 1vw;
        transition: all 0.2s;
    }

    .second-section {
        height: 80vh;
        width: 80vw;
        margin-top: 10vh;
        margin-bottom: 10vh;
        /* background-color: thistle; */
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
        /* background-color: tomato; */
    }

    .second-section .right {
        margin-left: 10%;
        width: 45%;
        height:55vh;
        position: absolute;
        right: 0;
        margin-right: 5vw;
        /* background-color: aqua; */
    }

    .second-section .right img {
        width: 100%;
        height: auto;
        margin-top: 3vh;
    }

    .video-play-button {
        text-decoration: none;
    }

    .second-section .left h1 {
        font-size: 2.5vw;
    }

    .second-section .left p {
        font-size: 1.1vw;
    }

    .third-section {
        height: 90vh;
        width: 100vw;
        margin-top: 10vh;
        margin-bottom: 20vh;
        /* background-color: thistle; */
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
        /* background-color: tomato; */
    }

    .third-section .right {
        margin-left: 10%;
        width: 45%;
        height:55vh;
        position: absolute;
        right: 0;
        margin-right: 6vw;
        /* background-color: aqua; */
        margin-top: -13vh;
    }

    .third-section .left img {
        width: 90%;
        height: auto;
        margin-top: -12vh;
        margin-left: 0vw;
        transform: rotate(-40deg);
    }

    .third-section .right h1 {
        font-size: 2.5vw;
    }

    .third-section .right p {
        font-size: 1.1vw;
    }

    #discord {
        margin-left: 0vw;
    }
</style>

<body>
    <div class="first-section">
        <div>
            <img src="/assets/images/illus-bg.png" alt="illus-bg">
        </div>
        <div class="text">
            <h1>ROBOTRONICS '21</h1>
            <p>26th July - 6th August </p>
            <div class="buttons">
                <span class="nav-link-button">Register</span>
                <a class="video-play-button" data-fancybox href="https://www.youtube.com/watch?v=oEr_jwRZ07A&feature=youtu.be">
                    <span class="watch">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24.534" height="24.534" viewBox="0 0 29.534 29.534" style="margin-right: 0.5vw;">
                            <path id="Icon_material-play-circle-outline" data-name="Icon material-play-circle-outline" d="M14.814,24.412l8.86-6.645-8.86-6.645ZM17.767,3A14.767,14.767,0,1,0,32.534,17.767,14.773,14.773,0,0,0,17.767,3Zm0,26.581A11.814,11.814,0,1,1,29.581,17.767,11.829,11.829,0,0,1,17.767,29.581Z" transform="translate(-3 -3)" fill="#00af3b"/>
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
            <p> Robotronics 2020, the 7th edition of Tech Syndicate's annual
                event, which saw participation from over 300+ students from 35
                schools and 40+ individual teams across Delhi NCR, was an
                astounding success.
                <br />
                <br />
                Participants across events exhibited their creativity by proposing
                solutions to societal problems, rebranding a fictional company,
                solving tasks of cryptography and steganography, and debating on
                topics like privatisation of NASA programs and the use of AI/ML to
                replace human judgement.
                <br />
                <br />
                Delhi Public School, R.K. Puram's Exun Clan emerged as the overall
                winners.</p>
        </div>
        <div class="right">
            <img src="/assets/images/tscircuitglow.png" alt="ts-illus-2-glow">
        </div>
    </div>
    <div class="third-section">
        <div class="left">
            <img src="/assets/images/ts3d.png" alt="ts-illus-2-glow">
        </div>
        <div class="right">
            <h1><span style="color: #16e16e; font-size: 2vw; font-weight: 550;">About</span></h1>
            <h1 style="margin-top: -4vh">Tech Syndicate</h1>
            <p>
                Established in 2016, Tech Syndicate is the technology club of
                Amity International School, Sector-46, Gurgaon. The club works
                constantly to encourage students to learn new technologies and
                keep up with the rapidly progressing sector of computer science.
                <br />
                <br />
                Through the years, it has transformed into a family of designers,
                developers, programmers, and filmmakers who dominate their fields.
                The members of the club have won several inter-school, national
                and international events, and have repeatedly brought accolades to
                the school.
                <br />
                <br />
                Robotronics, our annual tech symposium, was first hosted in 2013,
                and has since then been recognized as one of the most prominent
                competitions of the tech circuit. With a plethora of different
                events under it, Robotronics receives participation from 300+
                students across Delhi NCR.
            </p><br>
            <span class="nav-link-button" id="discord">Discord</span>
        </div>
    </div>
</body>