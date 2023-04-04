<script setup>
import { cart } from "./SideCart.js";
import { total } from "./SideCart.js";
</script>

<template>
  <div id="div" :class="theme">
    <h2>{{ title }}</h2>
    <h3>${{ price }}.00</h3>
    <p>Released {{ date }}</p>
    <img :src="getImage" alt="" />
    <button @click="addit" id="buy" :class="btntheme">Add To Cart</button>
  </div>
</template>

<script>
export default {
  name: "CardCool",
  data() {
    return {
      theme: "crddark",
      btntheme: "dark",
    };
  },
  props: {
    title: String,
    date: String,
    price: Number,
    img: String,
  },
  methods: {
    addit: function () {
      cart.push({
        name: this.title,
        cost: this.price,
      });
      total.value = total.value + 38;
    },
  },
  components: {},
  computed: {
    getImage: function () {
      return this.img;
    },
  },
};
</script>

<style scoped>
.crddark {
  background-color: black;
  color: white;
  border: 5px solid white;
  margin: 2vh 3vw;
  padding: 1vh 2vw;
  transition: 0.3s;
}
#div:hover {
  transform: scale(1.05);
}
img {
  width: 100%;
  border: 3px solid white;
}
.dark {
  width: 9em;
  color: white;
  background-color: black;
  border: 3px solid white;
  margin-top: 5px;
  font-weight: bold;
  transition: 0.3s;
  border-radius: 0;
}
.dark:hover {
  box-shadow: inset 10em 0 0 0 white;
  color: black;
}
</style>
