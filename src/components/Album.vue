<template>
  <div class="album text-center"
           >
           <div class="album-cover">
           <img :src="src" alt="">
           </div>
             <h3>{{titolo}}</h3>
             <p>{{autore}} {{anno}}</p>
          </div>
</template>

<script>
export default {
name: "Album",
props: {
    src: String,
    titolo: String,
    autore: String,
    anno: String,
}
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/partials/_variables.scss";
.album {
            width: calc(100% / 5 - 40px);
            margin-left: 40px;
            margin-bottom: 30px;
            height: 350px;
            background-color: $GrayColor;
            .album-cover {
                width: 70%;
                margin: 0 auto;
                margin-top: 20px;
                img {
                    width:100%;
                }
            }
            h3 {
                color: white;
                font-size: 1.6em;
                margin-top: 20px;
            }
            p {
                color: gray;
                font-size: 1.3em;
                margin-top: 30px;

            }
        }
</style>