<template>
  <div class="product-details">
    <div class="product-details-image">
        <img :src="product.image" class="image" alt="">
    </div>
    <div class="product-details-info">
        <div class="product-details-description">
            <small>{{product.manufacturer.name}}</small>
            <h3>{{product.name}}</h3>
            <p>
                {{product.description}}
            </p>
        </div>
        <div class="product-details-price-cart">
            <p>{{product.price}}</p>
            <product-button :product="product"></product-button>
        </div>
    </div>
  </div>
</template>

<script>
import ProductButton from './ProductButton';
export default {
    props: ['product'],
    components: {
        'product-button': ProductButton
    }
}

</script>
<style>
.product-details-image .image {
    width: 150px;
    height: 150px;
}
</style>