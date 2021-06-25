<svelte:head>
  <title>TS | Register</title>
</svelte:head>

<script>
    import Jumbotron from "../components/Jumbotron.svelte";
    import SchoolForm from "../components/SchoolForm.svelte";
    import IndiForm from "../components/IndiForm.svelte";
    let optionSelected = 1;
    window.addEventListener('click', (e) => {
      if(e.target.id === "opt1") {
        optionSelected = 1
      } else if (e.target.id === "opt2") {
        optionSelected = 2
      }
    })
</script>
  
<body>
  <Jumbotron
    title="Register"
    description="You can register with your school or as an independent team. Independent teams will not be eligible for the overall trophy. The deadline to register is July 12, 2021."
  />
  <div style="margin-top: 5vh"></div>
  <div class="first-section">
    <p>Registration Type</p>
    <div class="radios">
      {#if optionSelected === 1}
        <div class="option1 selected" id="opt1">
          <p id="opt1">School</p>
        </div>
      {:else}
        <div class="option1" id="opt1">
          <p id="opt1">School</p>
        </div>
      {/if}
      {#if optionSelected === 2}
        <div class="option2 selected" id="opt2">
          <p id="opt2">Independent</p>
        </div>
      {:else}
        <div class="option2" id="opt2">
          <p id="opt2">Independent</p>
        </div>
      {/if}
    </div>
    {#if optionSelected === 1}
      <SchoolForm/>
    {:else}
      <IndiForm/>
    {/if}
  </div>
  <div style="height: 18vh" />
</body>

<style>
  body {
    padding: 0 18%;
  }

  .first-section p {
    font-size: 1vw;
    color: #16e16e
  }

  .first-section .radios {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    background-color: transparent;
    height: 2.2vw;
    margin-top: -0.8vw;
    margin-bottom: 2.3vw;
    border-radius: 3px;
  }

  #opt1 {
    font-size: 1.2vw;
    margin-top: 0.4vw;
    color: white;
  }

  #opt1:hover {
    cursor: pointer;
  }

  #opt2 {
    font-size: 1.2vw;
    margin-top: 0.4vw;
    color: white;
  }

  #opt2:hover {
    cursor: pointer;
  }

  .option1 {
    width: 17.5vw;
    border: 0.01vw white solid;
    color: white;
    height: 2.2vw;
    text-align: center;
    border-radius: 3px;
    padding-top: 0.3rem;
    padding-bottom: 0.3rem;
  }

  .option2 {
    width: 20.4vw;
    border: 0.01vw white solid;
    height: 2.2vw;
    text-align: center;
    border-radius: 3px;
    margin-left: 2vw;
    padding-top: 0.3rem;
    padding-bottom: 0.3rem;
  }

  .selected {
    background-color: #00AF3B;
    border: 0.01vw #00AF3B solid;
  }

  @media screen and (max-width: 768px) {
    body {
      padding: 0 8%;
    }

    .first-section .radios {
      margin-bottom: 11vw;
    }
    
    .first-section p {
      font-size: 3vw;
    }

    .option1 {
      width: 35vw;
      height: 5vw;
    }

    .option2 {
      width: 35vw;
      height: 5vw;
      margin-left: 4vw;
    }

    #opt1 {
      font-size: 3.5vw;
      margin-top: 0.4vw;
      color: white;
    }

    #opt2 {
      font-size: 3.5vw;
      margin-top: 0.4vw;
      color: white;
    }
  }
</style>