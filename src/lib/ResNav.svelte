<script>
</script>

<div class="resNav">
  <ul class="resNav_links">
    <li class="resNav_link">Home</li>
    <li class="resNav_link">About</li>
    <li class="resNav_link">Loaders</li>
  </ul>
</div>

<style>
  .resNav {
    position: fixed;
    top: 10%;
    left: 0%;
    width: 100vw;
  }

  .resNav_links {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 0.1rem;
    text-align: center;
    background-color: rgba(255, 255, 255, 0.06);
    border: 1px solid rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(40px);
  }

  .resNav_link {
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
    text-decoration: none;
    transition: all 0.2s ease-in;
    color: rgba(0, 0, 0, 0.89);
    z-index: 999;
  }
  .resNav_link:hover{
    text-decoration: underline;
  }
</style>
