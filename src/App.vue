<template>
  <div id="page">
    <Header />
    <Product v-on:change-pack="filterContents"/>
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
      //console.log(pack);
      this.cont = pack;
      //console.log(this.cont);
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
