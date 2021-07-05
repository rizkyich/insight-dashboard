<template>
  <div id="insight-view">
    <Header/>

    <main>
      <SideNavigation/>
      <section class="content-container">
        <InsightContainer/>
      </section>
    </main>
  </div>
</template>

<script>
import Header from '@/components/Header'
import SideNavigation from '@/components/SideNavigation'
import InsightContainer from '@/components/InsightContainer.vue'

export default {
  components: { Header, SideNavigation, InsightContainer }
}
</script>

<style>
#insight-view {
  width: 100%;
  height: 100vh;
  /* background-color: red; */
}

main {
  width: 100%;
  height: calc(100vh - 64px);
  display: flex;
}
</style>