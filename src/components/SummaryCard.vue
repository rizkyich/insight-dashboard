<template>
  <div id="summary-card" class="card">
    <div class="card-head">
      <p class="text-gray">Sales Turnover</p>
      <button>
        <img src="@/assets/pagecontent/Icon - More - Filled.png"/>
      </button>
    </div>

    <div id="summary-content">
      <div class="summary-text">
        <h2>
          Rp 3,600,000
        </h2>
        <p class="sub-text">
          <img src="@/assets/pagecontent/DownArrow.png"/>
          <span>13.8%</span> last period in product sold
        </p>
      </div>
      <img class="summary-icon" src="@/assets/pagecontent/Sales Turnover.png"/>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style>
#summary-card {
  width: 276px;
  height: 104px;
  margin: .5rem 0;
}

.text-gray {
  font-size: 1rem;
  color: var(--clr-grey-3)
}

.card-content {
  width: 100%;
  height: auto;
  padding-top: .25rem;
}

#summary-content {
  display: flex;
}

.summary-icon {
  width: auto;
  height: 2.5rem;
  margin-left: 5px;
}

.summary-text h2 {
  color: var(--clr-grey-7)
}

.sub-text {
  color: var(--clr-grey-3);
  font-size: .75rem;
  margin-top: 2.5px;
}

.sub-text span{
  color: var(--clr-red-light)
}
</style>