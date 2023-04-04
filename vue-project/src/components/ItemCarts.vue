<script setup>
import CardCool from "./CardCool.vue";
import { cart } from "./SideCart.js";
import { total } from "./SideCart.js";
</script>

<template>
  <div class="shop">
    <h2>{{ item }}</h2>
    <p>${{ cost }}.00</p>
    <button class="remove" @click="removeit">Remove From Cart</button>
  </div>
</template>
<script>
export default {
  name: "ItemCarts",
  props: {
    item: String,
    cost: Number,
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
};
</script>
<style>
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
}
</style>
