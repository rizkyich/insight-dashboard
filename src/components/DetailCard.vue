<template>
  <div id="detail-card" class="card">
    <div class="card-head">
      <p class="text-gray">{{titleHead}}</p>
      <button>
        <img src="@/assets/pagecontent/Icon - More - Filled.png"/>
      </button>
    </div>

    <div class="card-content">
      <ListItem v-if="content !== 'chart'"/>
    </div>
  </div>
</template>

<script>
import ListItem from '@/components/ListItem.vue'

export default {
  props: ['content', 'titleindex'],
  components: { ListItem },
  data: () => ({
    textList: ['average purchase value', 'best selling sku', 'top competitor sku']
  }),
  computed: {
    titleHead() {
      return this.textList[this.titleindex].toUpperCase()
    }
  }
}
</script>

<style>
#detail-card {
  width: 100%;
  height: 100%;
  padding: 1rem 1rem 15px 1rem;
}

.card-content {
  width: 100%;
  min-height: 320px;
  margin-top: .5rem;
}
</style>