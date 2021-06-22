<script>
    export let member, role, image, website;
  </script>

<div class="wrap">
    <div class="card">
        <img src="{image}" alt="pfp"/>
        <h1>{member}</h1>
        <h2>{role}</h2>
    </div>
    <div class="specialization-div">
        <svg xmlns="http://www.w3.org/2000/svg" width="44.22" height="28.694" viewBox="0 0 44.22 28.694">
            <g id="Group_12" data-name="Group 12" transform="translate(1 1.31)" style="isolation: isolate">
            <g id="Icon_feather-code" data-name="Icon feather-code" transform="translate(0 4.205)">
                <path id="Path_10" data-name="Path 10" d="M24,26.665l10.663-8.832L24,9" transform="translate(7.558 -9)" fill="none" stroke="#00af3b" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"/>
                <path id="Path_11" data-name="Path 11" d="M13.663,9,3,17.832l10.663,8.832" transform="translate(-3 -9)" fill="none" stroke="#00af3b" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"/>
            </g>
            <line id="Line_16" data-name="Line 16" x1="10.979" y2="26.074" transform="translate(14.933)" fill="none" stroke="#00af3b" stroke-linecap="round" stroke-width="2"/>
            </g>
        </svg>
    </div>
</div>


<style>
    .wrap {
        display: flex;
        flex-flow: row wrap;
        align-items: center;
        margin-bottom: 10vh;
    }

    .card {
        border-radius: 32px;
        padding: 1.5vh 1.5vw;
        padding-top: 0.1vh;
        width: 13vw;
        height: 18vh;
        position: relative;
        background-color: #1A1A1B;
        text-align: center;
        z-index: 2;
    }

    .card h1 {
        font-weight: 500;
        font-size: 1.4vw;
        margin-top: 2vh;
    }

    .card h2 {
        font-weight: normal;
        font-size: 1vw;
        color: #16e16e;
        margin-top: -1vh;
    }

    img {
        height: 6.2vw;
        width: 6.2vw;
        border-radius: 50%;
        margin-top: -7vh;
        z-index: 3;
    }

    .specialization-div {
        background-color: #1A1A1B;
        height: 3.5vw;
        width: 3.5vw;
        margin-left: -1.5vw;
        margin-top: 7vh;
        border-radius: 10px;
        border: 0.25vw rgb(2, 2, 2) solid;
        z-index: 2;
    }

    .specialization-div svg{
        margin-left: 0.6vw;
        margin-top: 1vw;
    }
</style>