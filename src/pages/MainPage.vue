<template>
  <HeaderSite/>
  <main class="container">
    <ProductFilter/>
    <ProductList/>
  </main>
  
</template>

<script>
import HeaderSite from '@/components/header/HeaderSite.vue';
import ProductList from '@/components/product/ProductList.vue';
import ProductFilter from '@/components/filter/ProductFilter.vue';
export default {
  name: 'HomePage',
  components: {
    HeaderSite,
    ProductList,
    ProductFilter,
  }
}
</script>

<style scoped lang="scss">
  .container{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin-top: 24px;
  }
</style>