<script>
  import gif1 from "../assets/gif1.webm";
  import gif2 from "../assets/gif2.webm";
  import gif3 from "../assets/gif3.webm";
  import gif4 from "../assets/gif4.webm";
  import gif5 from "../assets/gif5.webm";
  import Typewriter from "svelte-typewriter";
</script>

<section class="Hero_sec">
  <div class="Hero_div">
    <div class="part_1">
      <div class="hero_text">
        <Typewriter>
          <h1 style="font-size: 2.5rem;">CSS Loader Generator</h1>
        </Typewriter>
        <button>Get Loader Now</button>
      </div>
    </div>

    <div class="part_2">
      <div class="angry-grid">
        <div id="item-0">
          <video src={gif2} class="gif" alt="gif1" autoplay loop />
        </div>
        <div id="item-1">
          <video src={gif3} class="gif" alt="gif1" autoplay loop />
        </div>
        <div id="item-2">
          <video src={gif1} class="gif" alt="gif1" autoplay loop />
        </div>
        <div id="item-3">
          <video src={gif5} class="gif" alt="gif1" autoplay loop />
        </div>
        <div id="item-4">
          <video src={gif4} class="gif" alt="gif1" autoplay loop />
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .Hero_sec {
    background: url("../assets/hero.png");
    width: 100vw;
    height: 90vh;
    background-repeat: no-repeat;
    background-size: 100vw 90vh;
    margin-top: 5rem;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    /* overflow: hidden; */
  }

  .Hero_div {
    position: absolute;
    top: 0%;
    left: 0%;
    width: 100vw;
    height: 80%;
    display: flex;
    justify-content: space-around;
    align-items: center;
    gap: 1rem;
    flex-wrap: wrap;
  }
  .part_1 {
    max-width: 35%;
    min-width: 25%;
    width: 40%;
    height: 100%;
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }
  .hero_text {
    padding-left: 4rem;
    font-family: "Poppins", sans-serif;
  }
  .hero_text > h1 {
    width: 28rem;
    letter-spacing: 1px;
    line-height: 4rem;
    font-weight: 1400;
    margin-bottom: 2rem;
    font-size: 60px;
  }
  .hero_text > button {
    width: 15rem;
    padding: 10px 2px;
    margin-top: 5rem;
    text-align: center;
    font-size: 1.2rem;
    font-weight: bold;
    background-color: #ad00ff;
    box-shadow: 3px 4px 6px 1px rgba(212, 210, 210, 0.515);
    border-radius: 10px;
    outline: none;
    outline-offset: none;
    transition: all 0.3s ease-in;
    border: none;
    cursor: pointer;
  }
  .hero_text > button:hover {
    background-color: #bb3bf6;
  }
  .part_2 {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 55%;
    height: 100%;
  }
  .angry-grid {
    min-width: 50%;
    width: 95%;
    height: 95%;
    padding-bottom: 8px;
    display: grid;
    grid-template-rows: repeat(10, 1fr);
    grid-template-columns: repeat(9, 1fr);
  }
  .angry-grid > div {
    position: relative;
  }
  .angry-grid .gif {
    position: absolute;
    filter: drop-shadow(6px 3px 8px grey);
    top: 0%;
    left: 0%;
    height: 100%;
    width: 100%;
  }
  #item-0 {
    background-color: #ff6d00;
    grid-row-start: 1;
    grid-column-start: 2;
    border-radius: 10px;
    grid-row-end: 3;
    grid-column-end: 4;
    box-shadow: 6px 4px 10px 2px #545353;
  }
  #item-1 {
    background-color: #4c7860;
    grid-row-start: 4;
    grid-column-start: 1;
    border-radius: 10px;
    grid-row-end: 7;
    grid-column-end: 4;
    box-shadow: 6px 4px 10px 2px #545353;
  }
  #item-2 {
    background-color: whitesmoke;
    grid-row-start: 2;
    grid-column-start: 5;
    border-radius: 10px;
    grid-row-end: 6;
    grid-column-end: 9;
    box-shadow: 6px 4px 10px 2px #545353;
  }
  #item-3 {
    background-color: #13298f;
    grid-row-start: 8;
    grid-column-start: 3;
    border-radius: 10px;
    grid-row-end: 11;
    grid-column-end: 6;
    box-shadow: 6px 4px 10px 2px #545353;
  }
  #item-4 {
    background-color: #fc5ad8;
    grid-row-start: 7;
    grid-column-start: 7;
    border-radius: 10px;
    grid-row-end: 9;
    grid-column-end: 9;
    box-shadow: 6px 4px 10px 2px #545353;
  }

  @media (max-width: 1160px) {
    .Hero_div {
      flex-direction: column-reverse;
      justify-content: space-between;
      position: absolute;
      top: 42vh;
    }
    .part_1 {
      max-width: 100%;
    }
    .angry-grid {
      width: 100%;
      max-width: 100%;
      padding-left: 10rem;
    }
  }

  @media (max-width: 768px) {
    .Hero_sec {
      background-size: 100% 100vh;
      height: 100vh;
    }
    .Hero_div {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    .part_2 {
      display: none;
    }

    .part_1 {
      width: 100%;
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }
  @media (max-width: 1160px) {
    .Hero_sec {
      background-size: 100% 100vh;
      height: 100vh;
    }

    .Hero_div {
      position: absolute;
      top: 0%;
    }
  }
</style>
