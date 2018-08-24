<template>
  <div class="product-list">
  	<h1>商品一覧</h1>
    <ul>
        <li v-for="{ id, name } in list" :key="id">
            <router-link :to="`/product/${ id }`">{{ name }}</router-link>
        </li>
    </ul>
  </div>
</template>

<script>
import products from "@/api/products.js";

export default {
  name: "ProductList",
  data() {
    return {

    };
  },
  computed: {
      list: () => products.fetch()
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
