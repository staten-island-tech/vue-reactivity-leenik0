<script setup>
import { cart } from "./SideCart.js";
import { total } from "./SideCart.js";
import ItemCarts from "./ItemCarts.vue";
</script>

<template>
  <div id="box">
    <div v-if="cart.length === 0">
      <button id="openbtn" @click="openbar">&#9776;</button>
    </div>
    <div v-else>
      <button id="openbtn" @click="openbar">{{ cart.length }}&#9776;</button>
    </div>
  </div>
  <div id="sidebar">
    <button id="closebtn" @click="closebar">&times;</button>
    <div v-if="cart.length === 0">
      <h2 class="totaltext">Nothing yet :/</h2>
    </div>
    <div v-else>
      <h2 class="totaltext">Total: ${{ total }}.00</h2>
      <ItemCarts
        v-for="carts in cart"
        :key="carts.name"
        :item="carts.name"
        :cost="carts.cost"
        :pic="carts.photo"
      ></ItemCarts>
      <button @click="checkout">Check Out</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "SideBar",
  methods: {
    openbar: function () {
      document.getElementById("sidebar").style.width = "250px";
      document.getElementById("box").style.marginRight = "250px";
    },
    closebar: function () {
      document.getElementById("sidebar").style.width = "0";
      document.getElementById("box").style.marginRight = "0";
    },
    checkout: function () {
      alert("lmao no");
    },
  },
  components: {
    ItemCarts,
  },
};
</script>
<style scoped>
#openbtn {
  color: white;
  background-color: transparent;
  padding: none;
  border: none;
}
#openbtn:active {
  border: none;
}

#closebtn {
  color: white;
  font-size: 1.5em;
  background-color: transparent;
  border: none;
  position: absolute;
  top: 0;
  left: 0;
}

#box {
  position: absolute;
  top: 0px;
  right: 0px;
  transition: 0.5s;
  padding: 1rem;
}
#sidebar {
  display: block;
  height: 100%;
  color: white;
  width: 0;
  text-align: center;
  position: fixed;
  z-index: 1;
  top: 0;
  right: 0;
  background-color: black;
  overflow-x: hidden;
  transition: 0.5s;
  border-left: 5px solid white;
}
#sidebar .totaltext {
  text-align: center;
  margin: auto;
  margin-top: 50px;
  transition: 0.5s;
}
</style>
