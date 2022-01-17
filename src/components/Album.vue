<template>
  <div class="album text-center"
           >
           <div class="album-cover">
           <img :src="src" alt="">
           </div>
             <h3>{{titolo}}</h3>
             <p>{{autore}}</p>
             <p>{{anno}}</p>
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
            padding: 20px;
            // height: 350px;
            background-color: $GrayColor;
            .album-cover {
                margin: 0 auto;
                // margin-top: 20px;
                img {
                    width:100%;
                }
            }
            h3 {
                color: white;
                font-size: 1.4em;
                margin-top: 20px;
                margin-bottom: 20px;
                text-transform: uppercase;

            }
            p {
                color: gray;
                font-size: 1em;


            }
        }
</style>