<template>
  <div
    class="good-item"
    v-on:mouseover="highlightGood()"
    v-on:mouseleave="unhighlightGood()"
  >
    <span class="likes-text" v-show="hovered">{{ good.likes }}</span>
    <span class="comments-text" v-show="hovered">{{ good.comments }}</span>
    <div class="img-container">
      <img :src="setImagePath" :alt="good.name" />
    </div>
    <h2>{{ good.name }}</h2>
    <div class="price">
      $ {{ good.price.toFixed(2) }}
      <!--Всегда оставлять 2 знака после запятой-->
    </div>
    <a class="buy-button" v-show="hovered" href="#">Add to Cart</a>
  </div>
</template>

<script>
export default {
  props: {
    good: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      hovered: false
    };
  },
  methods: {
    highlightGood: function() {
      if (!this.hovered) {
        this.hovered = true;
      }
      return;
    },
    unhighlightGood: function() {
      this.hovered = false;
    }
  },
  computed: {
    setImagePath() {
      return require(`@/assets/${this.good.imageUrl}`);
    }
  }
};
</script>

<style scoped>
.good-item {
  display: inline-block;
  text-align: center;
  position: relative;
  width: 355px;
  height: 452px;
  padding-top: 60px;
  box-sizing: border-box;
}
.good-item:hover {
  box-shadow: 1px 1px 10px 3px #f1f2f2;
}

.good-item:hover .price {
  color: #8c84f9;
}

.img-container {
  height: 236px;
  overflow: hidden;
}
.img-container img {
  width: auto;
  height: 100%;
}

.good-item h2 {
  font-family: "Open Sans", sans-serif;
  font-weight: 400;
  font-size: 1.125rem;
  margin-top: 20px;
  color: #929292;
  margin-bottom: 15px;
}

.price {
  font-family: "Open Sans", sans-serif;
  font-weight: 600;
  font-size: 1.5625rem;
  margin-bottom: 75px;
}

.comments-icon,
.likes-icon,
.likes-text,
.comments-text {
  position: absolute;
  top: 20px;
  font-family: "Open Sans", sans-serif;
  font-weight: 400;
  font-size: 0.875rem;
  color: #c4c4c4;
}

.likes-text {
  top: 18px;
  left: 50px;
}

.comments-text {
  top: 18px;
  right: 30px;
}

.likes-text::before {
  content: url("../assets/likes.png");
  top: 2px;
  position: absolute;
  left: -25px;
}

.comments-text::before {
  content: url("../assets/comments.png");
  top: 2px;
  position: absolute;
  left: -30px;
}

.buy-button {
  position: absolute;
  color: white;
  background-color: #9f69f5;
  padding: 20px 50px;
  display: inline-block;
  border-radius: 100px;
  bottom: -25px;
  left: 85px;
  font-family: "Open Sans", sans-serif;
  font-weight: 600;
  text-decoration: none;
}
</style>
