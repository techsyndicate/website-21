<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  const handleChange = () => {
    if (document.getElementById("searchBar").value.trim().length !== 0) {
      dispatch("message", {
        text: document.getElementById("searchBar").value,
      });
    } else {
      dispatch("message", {
        text: false,
      });
    }
  };
</script>

<div class="searchbar">
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 21.078 21.084">
    <path
      id="Icon_ionic-ios-search"
      data-name="Icon ionic-ios-search"
      d="M25.331,24.051l-5.862-5.917A8.354,8.354,0,1,0,18.2,19.418L24.025,25.3a.9.9,0,0,0,1.273.033A.908.908,0,0,0,25.331,24.051ZM12.9,19.489a6.6,6.6,0,1,1,4.666-1.932A6.556,6.556,0,0,1,12.9,19.489Z"
      transform="translate(-4.5 -4.493)"
      fill="#fff"
    />
  </svg>
  <input
    type="text"
    placeholder="Search"
    on:input={handleChange}
    id="searchBar"
  />
</div>

<style>
  .searchbar {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    border: none;
    border-bottom: 1px #16e16e solid;
    width: 20vw;
  }

  .searchbar svg {
    margin-bottom: 1.2vh;
    margin-right: 1vw;
    height: 0.9vw;
    width: 0.9vw;
  }

  .searchbar input {
    margin-bottom: 1.2vh;
    background-color: transparent;
    border: none;
    color: white;
    font-size: 1vw;
  }

  @media screen and (max-width: 768px) {
      .searchbar {
          width: 70vw;
          display: flex;
      }

      .searchbar svg {
          height: 2vh;
          width: 2vh;
          margin: 0;
          margin-right: 1vh;
          margin-bottom: 1vh;
      }

      .searchbar input {
          font-size: 2vh;
          margin-bottom: 1.2vh;
      }
  }
</style>
