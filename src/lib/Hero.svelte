<script>
  import Navbar from "./Navbar.svelte";
  import gif1 from '../assets/gif1.gif'
  import gif2 from '../assets/gif2.gif'
  import gif3 from '../assets/gif3.gif'
  import gif4 from '../assets/gif4.gif'
  import gif5 from '../assets/gif5.gif'
</script>

<section class="Hero_sec">
  <!-- <Navbar /> -->
  <div class="Hero_div">
    <div class="part_1">
      <div class="hero_text">
        <h1>CSS Loader Generator</h1>
        <button>Get Loader Now</button>
      </div>
    </div>

    <div class="angry-grid">
      <div id="item-0">
        <img src={gif2} class="gif" alt="gif1"/>
      </div>
      <div id="item-1"><img src={gif3} class="gif" alt="gif1"/></div>
      <div id="item-2"><img src={gif1} class="gif" alt="gif1"/></div>
      <div id="item-3"><img src={gif5} class="gif" alt="gif1"/></div>
      <div id="item-4"><img src={gif4} class="gif" alt="gif1"/></div>
    </div>
  </div>
</section>

<style>
  .Hero_sec {
    background: url("../assets/hero.svg");
    width: 100%;
    height: 100vh;
    background-repeat: no-repeat;
    background-size: cover;
    position: relative;
    /* overflow: hidden; */
  }

  @media (max-width: 768px) {
    .Hero_sec {
      background-size: 100% 100vh;
      height: 100vh;
    }
  }

  .Hero_div {
    width: 100%;
    height: 88%;
    display: flex;
    justify-content: center;
    align-items: center;
    /* background-color: pink; */
    gap: 1rem;
    position: absolute;
    top: 12vh;
    flex-wrap: wrap;
  }
  .part_1 {
    max-width: 35%;
    width: 40%;
    height: 100%;
    display: flex;
    /* background-color: #13298F; */
    justify-content: flex-start;
    align-items: center;
  }
  .hero_text {
    /* padding-left: 4rem; */
    font-family: "Poppins", sans-serif;
  }
  .hero_text >h1 {
    width: 28rem;
    letter-spacing: 1px;
    line-height: 4rem;
    font-weight: 1400;
    margin-bottom: 2rem;
    font-size: 60px;
  }
  .hero_text >button{
    width: 15rem;
    padding: 10px 2px;
    text-align: center;
    font-size: 1.2rem;
    font-weight: bold;
    background-color: #AD00FF;
    box-shadow: 3px 4px 6px 1px rgba(212, 210, 210, 0.515);
    border-radius: 10px;
    outline: none;
    outline-offset: none;
    border: none;
  }
  .angry-grid {
    max-width: 50%;
    width: 55%;
    height: 100%;
    /* background-color: rgb(255, 242, 255); */
    padding: 5em 2rem;
    display: grid;
    grid-template-rows: 1fr 1fr 1fr 1fr 1fr;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  }
  .angry-grid >div{
    position: relative;
  }
  .angry-grid  .gif{
    position: absolute;
    filter: drop-shadow(6px 3px 8px grey);
    top: 0%;
    left: 0%;
    height: 100%;
    width: 100%;
  }
  #item-0 {
    background-color: #FF6D00;
    grid-row-start: 1;
    grid-column-start: 1;
        border-radius:10px;
    grid-row-end: 2;
    grid-column-end: 3;
    margin: 1rem 1rem 1rem 4rem;
    height: 6em;
    width: 10em;
    box-shadow: 6px 4px 10px 2px #545353;
  }
  #item-1 {
    background-color: #4C7860;
    grid-row-start: 2;
    grid-column-start: 1;
    border-radius:10px;
    grid-row-end: 3;
    grid-column-end: 3;
    height: 10rem;
    width: 14rem;
    box-shadow: 6px 4px 10px 2px #545353;
  }
  #item-2 {
    background-color: whitesmoke;
    grid-row-start: 1;
    grid-column-start: 3;
    border-radius:10px;
    grid-row-end: 3;
    grid-column-end: 6;
    margin: 2rem 0 0rem 1rem;
    width: 22rem;
    height: 16rem;
    box-shadow: 6px 4px 10px 2px #545353;
  }
  #item-3 {
    background-color: #13298F;
    grid-row-start: 3;
    grid-column-start: 2;
    border-radius:10px;
    grid-row-end: 6;
    grid-column-end: 4;
    height: 8rem;
    width: 12rem;
    margin-left: 4rem;
    margin-top: 2rem;
    box-shadow: 6px 4px 10px 2px #545353;
  }
  #item-4 {
    background-color: #fc5ad8;
    grid-row-start: 3;
    grid-column-start: 4;
    border-radius:10px;
    grid-row-end: 5;
    grid-column-end: 4;
    height: 6rem;
    width: 10rem;
    margin-left: 4rem;
    margin-top: 2rem;
    box-shadow: 6px 4px 10px 2px #545353;
  }


  @media (max-width: 1160px){
    .Hero_div{
      /* flex-wrap: wrap-reverse; */
      flex-direction: column-reverse;
      justify-content: space-between;
      position: absolute;
    top: 42vh;
    }
    .part_1{
      max-width: 100%;
    }
    .angry-grid{
      width: 100%;
      max-width: 100%;
      padding-left: 10rem;
    }
  }
</style>
