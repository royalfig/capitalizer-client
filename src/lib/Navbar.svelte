<script>
  // your script goes here
</script>

<!-- markup (zero or more items) goes here -->

<nav class="navbar">
  <div class="navbar__inner">
    <div class="navbar__left">
      <h1><a href="/">Capitalizer</a></h1>
    </div>
    <div class="navbar__right" />
    <p>A lightning-fast title capitalization tool</p>
  </div>
</nav>

<style>
  .navbar {
    background-color: var(--dark-blue);
    padding: 0.5rem 2rem;
  }

  .navbar__inner {
    max-width: 1024px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: var(--light-red);
  }

  .navbar__left h1 {
    color: var(--light-red);
    position: relative;
    z-index: 1;
    font-weight: 400;
  }

  .navbar__left h1::before {
    height: 1em;
    width: 1em;
    background-color: var(--red);
    border-radius: 50%;
    content: "";
    position: absolute;
    left: 0;
    top: 50%;
    transform: translate(-25%, -50%);
    z-index: -1;
  }
</style>
