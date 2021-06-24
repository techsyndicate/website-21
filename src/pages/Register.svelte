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
    description="You can register with your school or as an independent team. Independent teams will not be eligible for the overall trophy. The deadline to register is July 11, 2021."
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
    /* border-top-right-radius: 0px;
    border-bottom-right-radius: 0px; */
  }

  .option2 {
    width: 20.4vw;
    border: 0.01vw white solid;
    /* background-color: thistle; */
    height: 2.2vw;
    text-align: center;
    border-radius: 3px;
    /* border-left-width: 0px;
    border-top-left-radius: 0px;
    border-bottom-left-radius: 0px; */
    margin-left: 2vw;
  }

  .selected {
    background-color: #00AF3B;
    border: 0.01vw #00AF3B solid;
  }

</style>