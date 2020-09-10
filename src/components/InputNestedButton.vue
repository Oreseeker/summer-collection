<template>
  <div class="input-nested-button">
    <input type="text" placeholder="Enter your e-mail address" />
    <button class="submit-letter">
      <slot>Submit</slot>
    </button>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
input[type="text"] {
  display: block;
  width: 53.125%; /*850px;*/
  height: 75px;
  margin: 0 auto;
  border-radius: 100px;
  border: 0;
  padding: 0 30px;
  font-family: "Open Sans", sans-serif;
  font-weight: 400px;
  font-size: 1.25rem;
  outline: none;
}

.submit-letter {
  font-family: "Open Sans", sans-serif;
  font-weight: 600;
  font-size: 1.25rem;
  color: white;
  position: absolute;
  right: 22%;
  top: 49.7%;
  background-color: #8c84f9;
  padding: 20px 65px;
  border-radius: 100px;
  cursor: pointer;
  border: 0;
  outline: 0;
}
</style>
