<template>
    <div class="container">
        <div class="header">
            <h1 class="header-title">BIOSKOP</h1>
        </div>
        <div class="movie_card" v-for="(data, index) in movie" :value="data" :key="index">
            <div class="info_section">
                     <div class="movie-item" @click="detailfilm(data.id)">
                        <img v-bind:src="data.image" class="img-fluid img-movie" v-bind:alt="data">
                <!-- ##IMPORT COMPONENT #1 ## -->
                        <!-- <Image :src="data.image"/> -->
                        <h3>{{data.title}}</h3>
                    <h3>{{data.release}} | {{data.duration}} | {{data.genre}} | {{data.age}}</h3>
                    <h4>Sutradara : {{data.director}}</h4>
                    <h4>Pemain : {{data.cast}}</h4>
                     </div>
            </div>
            <img class="blur_back"
            src="https://wallpaperaccess.com/full/249234.png"/>
        </div>
        <div class="footer">
            <h5>Copyright &copy;2020. Created by Anonymous. All rights reserved</h5>
        </div>
    </div>
</template>
<script>
import Img1 from '../assets/movie/habibie.jpg';
import Img2 from '../assets/movie/endgame.jpg';
import Img3 from '../assets/movie/parasite.jpg';
// ## IMPORT COMPONENT #3 ##
// import Image from '../assets/movie/image.vue';

export default {
//  ## IMPORT COMPONENT BUKAN HANYA FOTO #2 ##
  // components: { Image },
  data: () => ({
    movie: [
      {
        id: 1,
        title: 'Habibie & Ainun 3',
        // ## ini ditaruh di file yang ingin dituju #4 ##
        image: Img1,
        release: '19 Desember 2019',
        duration: '121 menit',
        genre: 'Biography, Drama, Romance',
        age: 'Semua Umur',
        director: 'Hanung Bramantyo',
        cast: 'Jefri Nichol · ‎Aghniny Haque · ‎Maudy Ayunda',
      },
      {
        id: 2,
        title: 'End Game Marvel',
        image: Img2,
        release: ' 24 April 2019',
        duration: '181 menit',
        genre: 'Fantasi/Fiksi, ilmiah',
        age: '17+',
        director: 'Anthony Russo, Joe Russo',
        cast: 'Robert Downey Jr  · ‎Chris Evans · Chris Hemsworth',
      },
      {
        id: 3,
        title: 'PARASITE (2019)',
        image: Img3,
        release: '24 Juni 2019',
        duration: '132 menit',
        genre: 'Comedy, Drama, Thriller',
        age: '17+',
        director: 'Bong Joon Ho',
        cast: 'Kang-ho Song · Sun-kyun Lee · Yeo-jeong Jo',
      },
    ],
  }),
  methods: {
    detailfilm(filmId) {
      this.$router.push({ name: 'detail', params: { id: filmId } });
    },
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css?family=Montserrat:300,400,700,800");

.img-movie {
        padding-top: 2%;
        width: 120px;
    }
.container {
        width: auto;
    }
    .header {
        padding: 50px;
        grid-column: 1/5;
        background-color: black;
        color: #fff;
        text-align: center;
    }
    .header-title {
      font-family: monospace;
      font-size: 70px;
      color: gold;
    }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.judul {
  background: black;
  margin: 50px auto;
  height: 100px;
  font-size: 85px;
}

html,
body {
  margin: 0;
  background: black;
  font-family: "Montserrat", helvetica, arial, sans-serif;
  font-size: 14px;
  font-weight: 00;
}


.movie_card {
  position: relative;
  display: block;
  width: 800px;
  height: 350px;
  margin: 80px auto;
}
.info_section {
  position: relative;
  width: 100%;
  height: 100%;
  background-blend-mode: multiply;
  z-index: 2;
  border-radius: 10px;
}
h1 {
  color: black;
  font-weight: 400;
}
h4 {
  color: #555;
  font-weight: 400;
}
.minutes {
  display: inline-block;
  margin-top: 15px;
  color: #555;
  padding: 5px;
  border-radius: 5px;
  border: 1px solid rgba(0, 0, 0, 0.05);
}
.type {
  display: inline-block;
  color: #959595;
  margin-left: 10px;
}

.text {
  color: #545454;
}

.movie_social {
  height: 10%;
  padding-left: 15px;
  padding-bottom: 20px;
}
ul {
  list-style: none;
  padding: 0;
}
li {
  display: inline-block;
  color: rgba(0, 0, 0, 0.3);
  transition: color 0.3s;
  transition-delay: 0.15s;
  margin: 0 10px;
}
:hover {
  transition: color 0.3s;
  color: rgba(0, 0, 0, 0.7);
}
i {
  font-size: 19px;
  cursor: pointer;
}
.blur_back {
  position: absolute;
  top: 0;
  z-index: 1;
  height: 100%;
  right: 0;
  background-size: cover;
  border-radius: 11px;
}

@media screen and (min-width: 768px) {

  .info_section {
    background: linear-gradient(to right, #e5e6e6 50%, transparent 100%);
  }

  .blur_back {
    width: 80%;
    background-position: -100% 10% !important;
  }
}

@media screen and (max-width: 768px) {

  .blur_back {
    width: 100%;
    background-position: 50% 50% !important;
  }


  .movie_desc {
    width: 100%;
  }

  .info_section {
    background: linear-gradient(to top, #e5e6e6 50%, transparent 100%);
    display: inline-grid;
  }
}


</style>
