<template>
  <div>
    <div class="products">
        <div class="container">
            This is ProductList
        </div>
        <!-- <template v-for="product in products"> -->
            <product-item :products="products"></product-item>
        <!-- </template> -->
    </div>
  </div>
</template>

<script>
import ProductItem from './ProductItem.vue';
export default {
    name: 'product-list',
    created(){
        if(this.products.length === 0) {
            this.$store.dispatch('allProducts')
        }
    },
    computed: {
        // a computed getter
        products() {
            // return this.$store.state.products;
            return this.$store.getters.allProducts;
        }
    },
    components: {
        'product-item': ProductItem
    },
    // methods: {
    //     addToCart(product) {
    //         this.$store.commit('ADD_TO_CART', {
    //             product
    //         });
    //     }
    // }
}

</script>
<style>
.product {
    border-bottom: 1px solid black;
}

.product_image {
    width: 200px;
    height: 150px;
}
</style>