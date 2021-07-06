<template>
  <div id="detail-card" class="card">
    <div class="card-head">
      <p class="text-gray">{{titleHead}}</p>
      <div class="button-head">
        <button class="card-period" v-if="content === 'chart'">
            <p>6 Months</p>
            <img src="@/assets/pagecontent/arrow-down-grey.png"/>
          </button>
        <button>
          <img src="@/assets/pagecontent/Icon - More - Filled.png"/>
        </button>
      </div>
    </div>

    <div class="card-content">
      <ListItem v-if="content !== 'chart'"/>
      <ChartContainer v-else/>
    </div>
  </div>
</template>

<script>
import ListItem from '@/components/ListItem.vue'
import ChartContainer from '@/components/ChartContainer.vue'

export default {
  props: ['content', 'titleindex'],
  components: { ListItem, ChartContainer },
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

.button-head {
  width: auto;
  height: 100%;
  display: flex;

}

.card-period {
  width: 6rem;
  height: 100%;
  margin-right: 1rem;
  border: var(--border);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 .5rem;
}

.card-period p {
  color: var(--clr-grey-7)
}
</style>