<template>
  <button><slot></slot></button>
</template>

<script>
export default {
  name: "ButtonStuff",
};
</script>

<style scoped>
button {
  color: white;
  background-color: black;
  border: 3px solid white;
  margin: auto 1vw;
  font-weight: bold;
  transition: 0.25s;
  border-radius: 0;
}
button:hover {
  box-shadow: inset -3em 0 0 0 white, inset 3em 0 0 0 white;
  color: black;
  transform: scale(1.1);
}
button:active {
  transform: scale(0.9);
}
</style>
