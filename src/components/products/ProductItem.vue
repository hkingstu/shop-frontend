<template>
  <!-- <div>
    <div class="product">
        <router-link :to="'/detail/' + product._id" class="product-link">
          <p class="product_name">产品名称：{{product.name}}</p>
          <p class="product_description">介绍：{{product.description}}</p>
          <p class="product_price">价格：{{product.price}}</p>
          <p class="product.manufacturer">生产厂商：{{product.manufacturer.name}}</p>
          <img :src="product.image" alt="" class="product_image">
        </router-link>
        <product-button :product="product"></product-button>
    </div>
  </div> -->
  <div class="products">
    <el-table
    class="table"
    :data="products"
    max-height="250">
      <el-table-column
        prop="name"
        label="产品名称"
        width="180">
      </el-table-column>
      <el-table-column
        prop="description"
        label="介绍"
        width="180">
      </el-table-column>
      <el-table-column
        prop="price"
        label="价格"
        width="180">
      </el-table-column>
      <el-table-column
        prop="manufacturer.name"
        label="生产厂商"
        width="180">
      </el-table-column>
      <!-- <el-table-column
        label="图片"
        width="200">
        <img :src="image" alt="" class="product__image">
      </el-table-column> -->
      <el-table-column
        label="操作"
        width="180">
        <template slot-scope="scope">
          <product-button :id="scope.row._id"></product-button>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
import ProductButton from './ProductButton.vue';
export default {
    name: 'product-item',
    props: ['products'],
    components: {
        'product-button': ProductButton
    }
}

</script>
<style>
.products {
  padding-top: 10px;
  text-align: center;
}
.table {
  margin:0 auto;
  width: 900px;
}
.el-table .cell {
  text-align: center;
  padding-top: 10px;
  padding-bottom: 10px;
}

</style>