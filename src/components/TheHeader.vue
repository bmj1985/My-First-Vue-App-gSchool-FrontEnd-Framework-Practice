<template>
  <header id="TheHeader">
    <img src="../../static/g-dino.png"/>
  </header>
</template>

<script>
export default {
  name: 'TheHeader'
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header {
  grid-row: 1 / 2;
  display: grid;
  grid-template-columns: 25% 50% 15%;
  grid-template-rows: 50% 50%;
  padding-top: 10px;
}

img {
  grid-row: 1/3;
  grid-column: 1/2;
  height: 100px;
  width: auto;
}
</style>
