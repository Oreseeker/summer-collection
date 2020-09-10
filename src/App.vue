<template>
  <div id="app">
    <!-- Start of bag section -->
    <substrate>
      <h1>Trendy Arrivals</h1>
      <div class="wrapper">
        <good-item v-for="bag in bags" :key="bag.id" :good="bag" />
      </div>
    </substrate>
    <!-- End of bag section -->
    <div class="brand-block">
      <image-text>
        <template v-slot:main-header>Our Brands</template>
        <template v-slot:small-header>
          Small shoes 2017 new arrivals mini Messenger
          <span class="h-purple">Classic Shoes</span>
        </template>
        <template v-slot:text>
          In porttitor elit ac mi placerat hendrerit. Morbi accumsan, erat in
          ullamcorper consectetur, nisi erat efficitur eros, sagittis tristique
          odio turpis vitae dui. Vestibulum gravida est ut erat pretium, non
          pretium diam feugiat. Integer egestas suscipit lorem ac fermentum.
          Integer at mauris vitae justo sagittis dapibus. Pellentesque sit amet
          nisl vitae orci vehicula faucibus. Fusce et lat, feugiat est
        </template>
      </image-text>
      <img src="@/assets/phone.png" id="phone"/>
    </div>
    <!-- Start of swtichable goods block-->
    <substrate>
      <section class="switchable-goods">
      <h1>Our Showcase</h1>
      <nav-bar :menu-items="menuItems" />
      <dropdown-menu :categories="menuItems"/>
      <div class="wrapper">
        <good-item v-for="watch in watches" :key="watch.id" :good="watch" />
      </div>
      </section>
    </substrate>
    <!-- End of switchable goods block -->
    <div class="newsletter-block">
      <h1>Newsletter</h1>
      <input-nested-button>Submit</input-nested-button>
    </div>
    <footer>
      <h1>Big Shop</h1>
      <nav-bar :menuItems="footerMenu" />
      <div class="our-links">
        <a href="www.facebook.com">
          <font-awesome-icon :icon="{ prefix: 'fab', iconName: 'facebook-f' }" />
        </a>
        <a href>
          <font-awesome-icon :icon="{ prefix: 'fab', iconName: 'google-plus-g' }" />
        </a>
        <a href="www.facebook.com">
          <font-awesome-icon :icon="{ prefix: 'fab', iconName: 'instagram' }" />
        </a>
        <a href="www.facebook.com">
          <font-awesome-icon :icon="{ prefix: 'fab', iconName: 'twitter' }" />
        </a>
      </div>
      <div class="copyright">&copy; Copyright 2017. Big Shop by Victor Themes.</div>
    </footer>
  </div>
</template>

<script>
import GoodItem from "./components/GoodItem.vue";
import Substrate from "./components/Substrate.vue";
import ImageText from "./components/ImageText.vue";
import NavBar from "./components/NavBar.vue";
import InputNestedButton from "./components/InputNestedButton.vue";
import DropdownMenu from "./components/DropdownMenu.vue";
export default {
  components: {
    GoodItem,
    Substrate,
    ImageText,
    NavBar,
    InputNestedButton, 
    DropdownMenu
  },
  data() {
    return {
      menuItems: [
        "Fashion",
        "Furnitures",
        "Watches",
        "Mobile",
        "Cloth",
        "Toys"
      ],
      footerMenu: ["Man", "Woman", "Kids", "Bags", "Watches", "Toys"],
      bags: [
        {
          id: 1,
          name: "Black Genuine Leather Bags",
          price: 23.2,
          imageUrl: "bag-1.png",
          likes: 1134,
          comments: 5430
        },
        {
          id: 2,
          name: "Fashion Red Leather Bags",
          price: 20.16,
          imageUrl: "bag-2.png",
          likes: 53,
          comments: 144
        },
        {
          id: 3,
          name: "Fashion Genuine Leather Bags",
          price: 30.14,
          imageUrl: "bag-3.png",
          likes: 236,
          comments: 541
        },
        {
          id: 4,
          name: "Simply Leather Bags",
          price: 15.2,
          imageUrl: "bag-4.png",
          likes: 18,
          comments: 1
        },
        {
          id: 5,
          name: "New Fashion Leather Bags",
          price: 25.2,
          imageUrl: "bag-5.png",
          likes: 24,
          comments: 5
        },
        {
          id: 6,
          name: "Single Hand Models Bags",
          price: 17.6,
          imageUrl: "bag-6.png",
          likes: 20,
          comments: 10
        }
      ],
      watches: [
        {
          id: 1,
          name: "Fashion Genuine Chain Watch",
          imageUrl: "watch-1.png",
          price: 25.36,
          likes: 35,
          comments: 24
        },
        {
          id: 2,
          name: "Fashion Silver Chain Watch",
          imageUrl: "watch-2.png",
          price: 35.24,
          likes: 0,
          comments: 0
        },
        {
          id: 3,
          name: "Fashion Chain Watch",
          imageUrl: "watch-3.png",
          price: 23.12,
          likes: 50,
          comments: 11
        },
        {
          id: 4,
          name: "Fashion Black Chain Watch",
          imageUrl: "watch-4.png",
          price: 43.22,
          likes: 12,
          comments: 36
        },
        {
          id: 5,
          name: "Fashion Leather Watch",
          imageUrl: "watch-5.png",
          price: 15.2,
          likes: 45,
          comments: 137
        },
        {
          id: 6,
          name: "Fashion Foreign Watch",
          imageUrl: "watch-6.png",
          price: 36.12,
          likes: 12,
          comments: 0
        }
      ]
    };
  }
};
</script>

<style>
html {
  font-size: 20px;
}
body {
  margin: 0;
}
#app {
  max-width: 1600px;
  margin: 0 auto;
}
.good-item {
  margin: 10px 5px;
}
.wrapper {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
}
.brand-block {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-evenly;
  align-items: center;
  width: 100%;
  margin-bottom: 100px;
  box-sizing: border-box;
}

.h-purple {
  color: #8c84f9;
}

.newsletter-block {
  overflow: hidden;
  position: relative;
  box-sizing: border-box;
  width: 100%;
  background-color: #8c84f9;
  height: 490px;
  margin-top: -70px;
  z-index: 1;
}

.newsletter-block h1 {
  position: relative;
  font-family: "Open Sans", sans-serif;
  font-weight: 700;
  font-size: 3.125rem;
  margin-top: 100px;
  margin-bottom: 80px;
  color: white;
  text-align: center;
  z-index: 1;
}

footer nav {
  width: 400px !important;
  padding: 0 !important;
}

footer {
  height: 400px;
  width: 100%;
}

footer h1 {
  box-sizing: border-box;
  font-family: "Roboto", sans-serif;
  font-weight: medium;
  font-size: 2.5rem;
  padding-top: 75px;
  text-align: center;
}

footer nav {
  display: flex;
  flex-direction: row;
  margin: 0 auto;
  justify-content: space-around;
  flex-wrap: wrap;
  margin-top: 45px;
  width: 32.5%; /* 520px */
}

footer nav a {
  color: #595959;
  font-family: "Open Sans", sans-serif;
  font-weight: 600;
  font-size: 1.125rem;
  display: block;
}

footer .our-links {
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  flex-wrap: wrap;
  width: 300px; /* 360px */
  margin-top: 60px;
  margin-bottom: 60px;
}

.our-links a {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50px;
  width: 50px;
  border-radius: 50%;
  box-shadow: 0 0 1px 3px #f1f2f2;
  background-color: white;
  color: black;
  font-size: 23px;
}

.our-links a:hover {
  color: white;
  background-color: #9971f6;
  box-shadow: none;
}

.our-links a i {
  color: inherit;
  font-size: 1.4375rem;
}

.copyright {
  padding: 25px 0;
  font-family: "Montserrat", sans-serif;
  font-size: 0.9375rem;
  font-weight: 300;
  background-color: #f6f5f7;
  color: #777777;
  text-align: center;
}

  .dropdown {
    display: none;
  }

@media screen and (max-width: 1160px) {
  .brand-block {
    padding: 40px;
  }
  .switchable-goods nav {
    width: 100%!important;
  }
}

@media screen and (max-width: 1145px) {
  html {
    font-size: 20px;
  }
  .brand-block {
    text-align: center;
    margin-top: 60px;
  }
}

@media screen and (max-width: 672px) {
  .switchable-goods nav {
    display: none!important;
  }
  .dropdown {
    display: block;
  }
}
@media screen and (max-width: 544px) {
  #phone {
    height: auto;
    width: 80%;
  }
}
@media screen and (max-width: 450px) {
  footer nav {
    flex-direction: column!important;
    box-shadow: none!important;
    border-radius: 0!important;
    width: 80%!important;
  }
  footer nav a {
    margin-bottom: 10px;
  }
}
</style>
