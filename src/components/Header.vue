<template>
  <header>
      <img src="https://upload.wikimedia.org/wikipedia/commons/7/71/Spotify.png" alt="">
  </header>
</template>

<script>
export default {
name: "Header",
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/partials/_variables.scss";
header {
  width: 100%;
  height: 60px;
  display: flex;
  align-items: center;
  background-color: $GrayColor;
  img {
    width: 45px;
    margin-left: 10px;
  }
}
</style>