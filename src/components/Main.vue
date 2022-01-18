<template>
  <main>
      <div class="container">
          <div class="selector">
                        <label  class="label-select" for="filter">FILTRA PER TIPO</label>
                            <select @change="filterAlbum" v-model="selected" id="filter">
                                <option class="All" value="All">All</option>
                            <option class="rock" value="Rock">Rock</option>
                            <option class="pop" value="Pop">Pop</option>
                            <option class="jazz" value="Jazz">Jazz</option>
                            <option class="metal" value="Metal">Metal</option>
                        </select>
         </div>
          <div class="albums">
          <!-- <div class="album text-center"
          v-for="(album, index) in arrayAlbum"
          :key="index"
           >
           <div class="album-cover">
           <img :src="album.poster" alt="">
           </div>
             <h3>{{album.title}}</h3>
             <p>{{album.author}} {{album.year}}</p>
          </div> -->
          <Album 
          v-for="(album, index) in newArray"
          :key="index"
          :src="album.poster"
          :titolo="album.title"
          :autore="album.author"
          :anno="album.year"
          />
          </div>
      </div>
  </main>
</template>

<script>
import axios from 'axios';
import Album from "./Album.vue";
// import func from 'vue-editor-bridge';
export default {
name: "Main",
components: {
    Album,
},
data() {
    return{
        arrayAlbum:null,
        albumGen: "",
        selected: "",
        newArray: null,

    }
},
mounted() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then((result) => {
        console.log(result.data.response);
        this.arrayAlbum = result.data.response;
        this.newArray = this.arrayAlbum;

    })
    .catch((error) => {
        console.log(error);
    })
},
methods: {
 filterAlbum() {
     console.log(this.albumGen);
     console.log(this.selected);
     console.log("array",this.arrayAlbum[0].genre);
    this.newArray = this.arrayAlbum.filter((element) => element.genre == this.selected)
    console.log("new", this.newArray);
    if (this.selected == "All") {
        this.newArray = this.arrayAlbum;
    }
    
 },
},
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/partials/_variables.scss";
.container {
    display: flex;
    background-color: $BgColor;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 60px;
    .albums {
        width: 70%;
        margin: auto;
        display: flex;
        flex-wrap: wrap;
        // .album {
        //     width: calc(100% / 5 - 40px);
        //     margin-left: 40px;
        //     margin-bottom: 30px;
        //     height: 350px;
        //     background-color: $GrayColor;
        //     .album-cover {
        //         width: 70%;
        //         margin: 0 auto;
        //         margin-top: 20px;
        //         img {
        //             width:100%;
        //         }
        //     }
        //     h3 {
        //         color: white;
        //         font-size: 1.6em;
        //         margin-top: 20px;
        //     }
        //     p {
        //         color: gray;
        //         font-size: 1.3em;
        //         margin-top: 30px;

        //     }
        // }
    }
}
</style>