<template>
  <div id="header-container">
    <div class="header-wrapper">
      <HeaderLogo/>

      <div class="userinfo-logout">
        <HeaderUser/>
        <LogoutButton/>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderLogo from '@/components/HeaderLogo.vue'
import HeaderUser from '@/components/HeaderUser.vue'
import LogoutButton from '@/components/LogoutButton.vue'

export default {
  components: { HeaderLogo, HeaderUser, LogoutButton }
}
</script>

<style>
  #header-container {
    position: relative;
    width: 100%;
    height: 64px;
    background-color: var(--clr-white);
    box-shadow: var(--dark-shadow);
  }

  .header-wrapper {
    height: 100%;
    width: 100%;
    max-width: var(--max-width);
    margin: 0 auto;
    padding: 0 2.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .userinfo-logout {
    width: auto;
    height: auto;
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 2.5rem;
  }
</style>