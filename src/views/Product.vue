<template>
  <div class="product">
  	<h1>商品情報</h1>
    <p>このページは ID. {{ id }} の詳細を表示する</p>
  </div>
</template>

<script>
export default {
  name: "Product",
  props: { id: Number },
  data() {
    return {

    };
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
