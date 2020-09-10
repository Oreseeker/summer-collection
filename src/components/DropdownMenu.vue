<template>
  <div class="dropdown">
    <div class="dropdown-header" @click="displayDropdown()">{{selectedCategory}}</div>
    <div class="dropdown-main" v-show="enabled">
      <div
        class="dropdown-element"
        v-for="category in categories"
        :key="category"
        @click="pickCategory(category)"
        v-show="category != selectedCategory"
      >{{ category }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    categories: {
      type: Array
    }
  },
  data() {
    return {
      enabled: false,
      selectedCategory: "Select category"
    };
  },
  methods: {
    displayDropdown() {
      this.enabled = !this.enabled;
    },
    pickCategory(category) {
      this.selectedCategory = category;
      this.enabled = false;
    }
  }
};
</script>

<style scoped>
.dropdown {
  width: 220px;
  margin-left: 50%;
  transform: translate(-50%, 0);
  text-align: center;
  font-size: 18px;
  font-family: "Open Sans", sans-serif;
  font-weight: 600;
  box-shadow: 10px 10px 30px 3px #f1f2f2;
}
.dropdown-header,
.dropdown-element {
  box-sizing: border-box;
  height: 50px;
}
.dropdown-header {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 0 20px;
}
.dropdown-header::after {
  position: absolute;
  right: 15px;
  top: 17px;
  content: "";
  border-right: 2px solid black;
  border-bottom: 2px solid black;
  width: 10px;
  height: 10px;
  transform: rotate(45deg);
}
.dropdown-element {
  margin: 10px 0;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>