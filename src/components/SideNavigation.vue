<template>
  <nav>
    <div id="burger-wrapper">
      <button class="nav-icon burger-button">
        <div class="burger-line"></div>
        <div class="burger-line"></div>
        <div class="burger-line"></div>
      </button>
    </div>

    <button class="nav-btn-wrapper selected">
        <div class="nav-icon">
          <img src="@/assets/nav/Dashboard icon.png"/>
        </div>
    </button>
  </nav>
</template>

<script>
export default {

}
</script>

<style>
  nav {
    width: 72px;
    height: 100%;
    background-color: var(--clr-white);
    border-right: var(--border);
  }

  .nav-btn-wrapper, #burger-wrapper {
    width: 100%;
    height: 48px;
    display: grid;
    place-items: center;
  }

  .selected {
    background-color: var(--clr-grey-5);
  }

  #burger-wrapper {
    margin-top: 1.5rem;
  }

  .nav-icon {
    position: relative;
    width: 24px;
    padding: 2px;
    background-color: var(--clr-white);
    border-radius: var(--radius);
  }

  .burger-button {
    height: 100%;
    padding: unset;
    background-color: unset;
    border-radius: unset;
  }

  .burger-button:hover .burger-line {
    background-color: var(--clr-grey-2);
  }

  .burger-line {
    position: relative;
    width: 100%;
    height: 2px;
    border-radius: var(--radius);
    background-color: var(--clr-grey-4);
    transition: var(--transition);
  }

  .burger-line:nth-of-type(2) {
    margin: 7px 0;
  }

  .burger-line:nth-last-child(1) {
    width: 80%;
  }
</style>