<template>
  <div class="product-item" :style="{height: product.id === 0 ? '80px' : '60px', borderTop: product.id !== 0 && 'var(--border)', borderBottom: product.id === 4 && 'var(--border)', backgroundColor: product.id === 0 && 'var(--clr-cream)' }">
    <div class="product-image" :style="{width: product.id === 0 ? '80px' : '60px'}">
      <img src="@/assets/pagecontent/Product  Competitor@2x.png"/>
    </div>

    <div class="product-info">
      <p class="product-name">{{product.name}}</p>
      <div class="product-detail">
        <p>{{product.price}}</p>
        <p>{{product.totalSold}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['product']
}
</script>

<style>
.product-item {
  width: 100%;
  margin: .5rem 0;
  display: flex;
  align-items: center;
}

.product-image {
  height: 100%;
}

.product-image img {
  width: 100%;
  height: 100%;
}

.product-info {
  flex: 1;
  height: 52px;
  padding: .5rem .5em;
}

.product-name {
  color: var(--clr-black);
}

.product-detail {
  width: 100%;
  height: auto;
  margin-top: auto;
  display: flex;
  justify-content: space-between;
  margin-top: 5px;
}

.product-detail p {
  font-size: .8rem;
  color: var(--clr-grey-3)
}
</style>