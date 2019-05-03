<template>
  <div id="page">
    <Header />
    <Product v-on:change-pack="filterContents" />
    <HowTo />
    <Contents :filtered="cont" />
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
  methods : {
    filterContents(pack) {
      this.cont = pack;
    }
  },
  data() {
    return {
      cont : {}
    }
  }
}
</script>

<style lang="scss">
@import "styles/fonts.scss";
@import "styles/app.scss";
  
</style>
