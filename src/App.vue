<template>
  <div id="page">
    <Header />
    <Product />
    <HowTo />
    <Contents />
  </div>
</template>

<script>

import Header  from './components/Header.vue';
import Product from './components/Product.vue';
import HowTo from './components/HowTo.vue';
import Contents from './components/Contents.vue';


export default {
  name: 'app',
  components: {
    Header,
    Product,
    HowTo,
    Contents
  },
  data() {
    return {
      
    }
  }
}
</script>

<style lang="scss">
@import "styles/fonts.scss";
@import "styles/app.scss";
  
</style>
