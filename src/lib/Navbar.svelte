<script>
  import logo from "../assets/logo.jpg";
  let windowWidth = window.innerWidth;
  let clicked = false;
  function handleResize() {
    windowWidth = window.innerWidth;
    if (windowWidth >= 640) clicked = false;
  }
  const handleClick = () => (clicked = !clicked);
  const resetClick = () => (clicked = false);
</script>

<svelte:window on:resize={handleResize} />
<header class="header">
  <nav class="nav">
    <div class="logo-block">
      <img src={logo} alt="logo" class="logo" />
      <h4 class="logoName">CSS LOADERS</h4>
    </div>
    <ul class="nav_links">
      <li class="nav_link">Home</li>
      <li class="nav_link">About</li>
      <li class="nav_link">Loaders</li>
      <button class="burger" on:click={handleClick}
        ><i class={clicked ? "fa fa-times" : "fas fa-bars"} /></button
      >
    </ul>
  </nav>
</header>

<style>
  .header {
    width: 100%;
    height: 11vh;
    padding: 10px 36px;
    position: fixed;
    top: 0%;
    left: 0%;
    z-index: 999;
    margin-bottom: 1rem ;
    background-color: #181a1c;
  }
  .nav {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .logo-block {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 15rem;
    height: 100%;
  }
  .logo-block img {
    width: 30%;
    height: 100%;
    border-radius: 20px;
  }
  .logo-block .logoName {
    font-size: larger;
    letter-spacing: 1px;
  }
  .nav_links {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    gap: 2.5rem;
    padding-right: 4rem;
  }
  .nav_links .nav_link {
    list-style: none;
    font-size: large;
    font-weight: 600;
    letter-spacing: 1px;
    cursor: pointer;
    position: relative;
    transition: 0.3s ease;
    text-decoration: none;
    border-bottom: 4px solid transparent;
    padding: 20px 0;
    margin: 0 5px;
  }
  .nav_links .nav_link:hover {
    border-bottom: 4px solid white;
    padding: 6px 0;
  }

  .nav_links .burger {
    display: none;
    font-size: x-large;
    width: 2rem;
  }

  @media (max-width: 768px) {
    .logo-block {
      width: 4rem;
    }
    .logo-block img {
      width: 100%;
      height: 100%;
      border-radius: 20px;
    }
    .logo-block .logoName {
      display: none;
    }
  }

  @media (max-width: 640px) {
    .nav_links .nav_link {
      display: none;
    }
    .nav_links .burger {
      display: block;
    }
  }
</style>
