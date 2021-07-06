<template>
  <div class="page-content">
    <div id="date-container">
      <DateRange/>
    </div>

    <PageTitle text="Dashboard"/>
    <PageSubTitle text="Market Insights"/>
    <SummaryCard/>
    <div class="insight-wrapper">
      <DetailCard content="chart" :titleindex="0"/>
      <DetailCard content="bestselling" :titleindex="1"/>
      <DetailCard content="topcompetitor" :titleindex="2"/>
    </div>
  </div>
</template>

<script>
import PageTitle from '@/components/PageTitle.vue'
import PageSubTitle from '@/components/PageSubTitle.vue'
import SummaryCard from '@/components/SummaryCard.vue'
import DetailCard from '@/components/DetailCard.vue'
import DateRange from '@/components/DateRange.vue'

export default {
  components: { PageTitle, PageSubTitle, SummaryCard, DetailCard, DateRange }
}
</script>

<style>
.insight-wrapper {
  width: 100%;
  height: 424px;
  margin-top: 1rem;
  margin-bottom: 32px;
  display: grid;
  grid-template-columns: 570px 275px 275px;
  justify-content: space-between;
}

#date-container {
  position: absolute;
  top: 0;
  right: 0;
  width: 481px;
  height: 48px;
}
</style>