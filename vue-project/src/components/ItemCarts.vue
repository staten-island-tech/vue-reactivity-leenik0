<script setup>
import CardCool from "./CardCool.vue";
import { cart } from "./SideCart.js";
import { total } from "./SideCart.js";
</script>

<template>
  <div class="shop">
    <div class="cartbox">
      <div>
        <h2>{{ item }}</h2>
        <p>${{ cost }}.00</p>
      </div>
      <img :src="getPic" alt="Album Photo" />
    </div>
    <button class="remove" @click="removeit">Remove From Cart</button>
  </div>
</template>
<script>
export default {
  name: "ItemCarts",
  props: {
    item: String,
    cost: Number,
    pic: String,
  },
  methods: {
    removeit: function () {
      const index = cart.findIndex((el) => el.name === this.item);
      if (index > -1) {
        cart.splice(index, 1);
      } else {
        console.log("hnnnngh");
      }
      total.value = total.value - 38;
    },
  },
  components: {
    CardCool,
  },
  computed: {
    getPic: function () {
      return this.pic;
    },
  },
};
</script>
<style>
.cartbox {
  display: flex;
  justify-content: space-between;
}
.cartbox img {
  max-width: 5vw;
  margin: 10px;
}

.shop {
  border-top: 3px solid white;
  border-bottom: 3px solid white;
  padding-bottom: 15px;
  padding-left: 1vw;
  margin: 10px 0px;
  text-align: left;
}
.remove {
  font-size: 85%;
  padding: 5px 8px;
  background-color: transparent;
  border: 2px solid white;
  border-radius: 0;
  color: white;
  transition: 0.3s;
}
.remove:hover {
  box-shadow: inset 10em 0 0 0 white;
  color: black;
  border-color: white;
}
</style>
