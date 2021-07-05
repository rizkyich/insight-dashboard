<template>
  <div id="header-logo">
    <img class="main-logo" alt="advotics logo" src="@/assets/header/advotics-logo.png"/>
    <sub class="poweredby-text">
      <p>powered by</p>
      <img class="sub-logo" alt="advotics logo" src="@/assets/header/advotics-logo.png"/>
    </sub>
  </div>  
</template>

<script>
export default {

}
</script>

<style>
  #header-logo {
    position: relative;
    width: auto;
    height: 32px;
    display: flex;
  }

  .main-logo, .sub-logo {
    width: auto;
    height: 100%;
  }

  .main-logo {
    cursor: pointer;
  }

  .poweredby-text {
    width: auto;
    height: 16px;
    display: flex;
    margin: auto 0 0 6.85px;
  }

  .poweredby-text p {
    width: 100%;
    margin-right: 5px;
    color: var(--clr-grey-2);
    cursor: default;
  }
</style>