<template>
  <div>
    <div class="title">
        <h1>{{msg}}</h1>
          <product-item :products="cart"></product-item>
    </div>
  </div>
</template>

<script>
import ProductItem from '@/components/products/ProductItem.vue'
export default {
    name: 'home',
    data() {
      return {
        msg: 'Welcome to the Cart Page'
      }
    },
    computed: {
      cart() {
        return this.$store.state.cart;
      }
    },
    components: {
      'product-item': ProductItem
    }
}

</script>
<style>
.product {
  border-bottom: 1px solid black;
}

.product_image {
  width: 150px;
  height: 150px;
}
</style>