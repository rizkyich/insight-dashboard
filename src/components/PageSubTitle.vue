<template>
  <div class="page-subtitle">
    <h3>{{text.toUpperCase()}}</h3>
    <div class="help-page">
      <button class="btn-help">
        <img src="@/assets/pagecontent/bulb.png"/>
        <p>Click here for help</p>
      </button>
      <img src="@/assets/pagecontent/arrow-up.png"/>
    </div>
  </div>
</template>

<script>
export default {
  props: ['text']
}
</script>

<style>
.page-subtitle {
  width: 100%;
  height: 48px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 1rem;
  background-color: var(--clr-green-dark);
  border-radius: var(--radius);
  margin: 1rem 0;
}

.page-subtitle h3 {
  color: var(--clr-white);
}

.help-page {
  width: auto;
  height: 20px;
  display: flex;
}

.btn-help {
  display: flex;
  align-items: center;
}

.help-page button p {
  color: var(--clr-white);
  text-decoration: underline;
  margin: 0 1rem 0 2px;
}
</style>