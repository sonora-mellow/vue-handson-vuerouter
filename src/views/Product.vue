<template>
  <div class="product" v-if="item" key="product">
  	<h1>{{ detail.name }}</h1>
      <nav class="nav">
        <router-link :to="{ name: 'product-name' }">商品詳細</router-link>
        <router-link :to="{ name: 'product-review' }">レビュー</router-link>
      </nav>
    </div>
    <div v-else key="loading">商品情報を読み込んでいます...</div>
</template>

<script>
import { mapGetters } from "vuex";
import products from "@/api/products.js";

export default {
  name: "Product",
  props: { id: Number },
  computed: mapGetters("product", ["detail"]),
  watch: {
    id: {
      handler() {
        products.asyncFind(this.id, item => {
          this.item = item
        })
      }, immediate: true
    }
  },
  beforedestroy() {
    this.$store.dispath("product/destroy")
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
