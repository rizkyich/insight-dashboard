<template>
  <div class="list-item">
    <ProductItem v-for="(product, index) in products" :key="index" :product="product"/>
  </div>
</template>

<script>
import ProductItem from '@/components/ProductItem'

export default {
  components: { ProductItem },
  data: () => ({   
    products: [
      {
        id: 0,
        name: '[Name Product]',
        totalSold: '[Jml Terjual]',
        price: 'Rp XXXX'
      },
      {
        id: 1,
        name: '[Name Product]',
        totalSold: '[Jml Terjual]',
        price: 'Rp XXXX'
      },
      {
        id: 2,
        name: '[Name Product]',
        totalSold: '[Jml Terjual]',
        price: 'Rp XXXX'
      },
      {
        id: 3,
        name: '[Name Product]',
        totalSold: '[Jml Terjual]',
        price: 'Rp XXXX'
      },
      {
        id: 4,
        name: '[Name Product]',
        totalSold: '[Jml Terjual]',
        price: 'Rp XXXX'
      }
    ]
  })
}
</script>

<style>
.list-item {
  width: 100%;
  height: auto;
}
</style>