<template>
  <main>
      <div class="container">
          <div class="albums">
          <div class="album text-center"
          v-for="(album, index) in arrayAlbum"
          :key="index"
           >
           <div class="album-cover">
           <img :src="album.poster" alt="">
           </div>
             <h3>{{album.author}}</h3>
             <p>{{album.author}} {{album.year}}</p>
          </div>
          </div>
      </div>
  </main>
</template>

<script>
import axios from 'axios';
export default {
name: "Main",
data() {
    return{
        arrayAlbum:null,
    }
},
mounted() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then((result) => {
        console.log(result.data.response);
        this.arrayAlbum = result.data.response;
    })
    .catch((error) => {
        console.log(error);
    })
}
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/partials/_variables.scss";
.container {
    display: flex;
    background-color: $BgColor;
    .albums {
        width: 70%;
        margin: auto;
        display: flex;
        flex-wrap: wrap;
        .album {
            width: calc(100% / 5 - 40px);
            margin-left: 40px;
            margin-bottom: 30px;
            height: 350px;
            background-color: $GrayColor;
            .album-cover {
                width: 70%;
                margin: 0 auto;
                img {
                    width:100%;
                }
            }
            h
        }
    }
}
</style>