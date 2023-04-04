<script setup>
import { cart } from "../src/components/SideCart.js";
</script>

<template>
  <img
    class="header"
    src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/ba/Rammstein_logo_3.svg/1280px-Rammstein_logo_3.svg.png"
    alt=""
  />
  <SideBar></SideBar>
  <div class="home">
    <CardCool
      v-for="album in albums"
      :key="album.name"
      :title="album.name"
      :date="album.date"
      :price="album.price"
      :img="album.img"
    ></CardCool>
  </div>
</template>
<script>
import ButtonStuff from "../src/components/ButtonStuff.vue";
import CardCool from "../src/components/CardCool.vue";
import SideBar from "../src/components/SideBar.vue";

export default {
  name: "AboutThing",
  components: {
    ButtonStuff,
    CardCool,
    SideBar,
  },
  data() {
    return {
      selected: "",
      albums: [
        {
          name: "Herzeleid",
          date: "September 1995",
          price: 38,
          img: "https://upload.wikimedia.org/wikipedia/en/thumb/1/1f/Rammstein_Herzeleid_cover.jpg/220px-Rammstein_Herzeleid_cover.jpg",
        },
        {
          name: "Sehnsucht",
          date: "August 1997",
          price: 38,
          img: "https://upload.wikimedia.org/wikipedia/en/thumb/b/b0/Rammstein_-_Sehnsucht.jpg/220px-Rammstein_-_Sehnsucht.jpg",
        },
        {
          name: "Mutter",
          date: "April 2001",
          price: 38,
          img: "https://upload.wikimedia.org/wikipedia/en/thumb/5/5e/Mutter.jpg/220px-Mutter.jpg",
        },
        {
          name: "Reise, Reise",
          date: "September 2004",
          price: 38,
          img: "https://upload.wikimedia.org/wikipedia/en/thumb/a/a0/ReiseReise.jpg/220px-ReiseReise.jpg",
        },
        {
          name: "Liebe ist für alle da",
          date: "October 2009",
          price: 38,
          img: "https://upload.wikimedia.org/wikipedia/en/thumb/9/98/Cover_lifad.jpg/220px-Cover_lifad.jpg",
        },
        {
          name: "Untitled Album",
          date: "May 2019",
          price: 38,
          img: "https://upload.wikimedia.org/wikipedia/en/thumb/1/16/Rammstein_-_Rammstein.png/220px-Rammstein_-_Rammstein.png",
        },
        {
          name: "Zeit",
          date: "April 2022",
          price: 38,
          img: "https://upload.wikimedia.org/wikipedia/en/thumb/a/ab/Rammstein_-_Zeit.png/220px-Rammstein_-_Zeit.png",
        },
      ],
    };
  },
  computed: {},
  methods: {},
};
</script>
<style>
.home {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
body {
  background-color: black;
}
</style>
<style scoped>
img {
  margin-top: 2vh;
}
</style>
