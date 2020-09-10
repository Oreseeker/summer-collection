<template>
  <div class="substrate">
    <slot></slot>
  </div>
</template>

<style scoped>
.substrate {
  width: 86.25%; /* 1380px */
  margin: 0 auto;
  padding: 7.2464% 0 10.5797% 0; /* 100 0 146 0 px*/
  background-color: white;
  position: relative;
  z-index: 100;
  box-sizing: border-box;
  box-shadow: 10px 10px 30px -20px #f1f2f2;
  background-color: white;
}

.substrate h1 {
  font-family: "Open Sans", sans-serif;
  font-weight: bold;
  text-align: center;
  margin-bottom: 50px;
}
</style>
