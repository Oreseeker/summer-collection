<template>
  <nav class="goods-categories">
    <a v-for="item in menuItems" :key="item.id">{{ item }}</a>
  </nav>
</template>

<script>
export default {
  props: {
    menuItems: {
      required: true,
      type: Array,
      id: {
        required: false,
        type: Number
      }
    }
  }
};
</script>

<style scoped>
nav.goods-categories {
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  width: 76.8116%; /*1060px;*/
  justify-content: space-around;
  overflow: hidden;
  border-radius: 100px;
  box-sizing: border-box;
  padding: 2.7778% 8.3333%; /*30px 90px;*/
  box-shadow: 10px 10px 30px 3px #f1f2f2;
  color: #333333;
}

nav.goods-categories a {
  display: block;
  font-size: 0.9375rem; /*1.25rem;*/
  color: black;
  font-family: "Open Sans", sans-serif;
  font-weight: 600;
  cursor: pointer;
}

nav.goods-categories a.active {
  color: #8c84f9;
  font-size: 1.25rem;
  margin-top: -5px;
}
</style>
