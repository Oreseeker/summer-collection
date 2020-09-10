<template>
  <div class="image-text">
    <h1>
      <slot name="main-header"> </slot>
    </h1>
    <h2>
      <slot name="small-header"> </slot>
    </h2>
    <div class="image-comments">
      <slot name="text"> </slot>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.image-text {
  width: 520px;
}

.image-comments {
  font-size: 1rem;
  font-family: "Open Sans", sans-serif;
  font-weight: 400;
  color: #777777;
}

.image-text h1 {
  font-family: "Open Sans", sans-serif;
  font-weight: 700;
  font-size: 3.125rem;
  margin-bottom: 40px;
}

.image-text h2 {
  font-family: "Open Sans", sans-serif;
  font-weight: 400;
  font-size: 1.5625rem;
  margin-bottom: 35px;
}
</style>
