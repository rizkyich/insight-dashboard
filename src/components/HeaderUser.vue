<template>
  <div id="header-user">
    <div class="user-text-info">
      <h4>Username</h4>
      <p>Company Name</p>
    </div>
    <img id="user-profile" alt="profile image" src="@/assets/header/Profile.png" />
  </div>
</template>

<script>
export default {

}
</script>

<style>
  #header-user {
    width: auto;
    height: 32px;
    display: flex;
  }

  .user-text-info {
    text-align: right;
    margin-right: 1rem;
  }

  .user-text-info h4 {
    font-size: 1rem;
    color: var(--clr-grey-2);
  }

  .user-text-info p {
    font-size: .85rem;
    color: var(--clr-grey-3);
  }

  #user-profile {
    height: 100%;
    width: auto;
  }
</style>