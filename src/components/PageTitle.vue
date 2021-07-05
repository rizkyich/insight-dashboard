<template>
  <div class="titlepage-wrapper">
    <h1>{{text}}</h1>
  </div>
</template>

<script>
export default {
  props: ['text']
}
</script>

<style>
.titlepage-wrapper {
  width: 100%;
  height: 50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.5rem;
}

.titlepage-wrapper h1 {
  color: var(--clr-grey-6)
}
</style>