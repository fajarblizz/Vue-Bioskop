<template>
    <div class="container">
        <div class="header">
            <h1 class="header-title">Bioskop</h1>
        </div>
    <!-- ## MENAMPILKAN DATA ARRAY LIST ## -->
    <!-- ## AGAR HEADER DAPAT MEMAKAI ARRAY HARUS PALING ATAS ## -->
        <div class="movie" v-for="(data, index) in movie" :value="data" :key="index">
    <!-- ## MENAMPILKAN ARRAY LIST ID CUMA 1 ## -->
            <div class="movie-item" v-if="filmId == data.id">
                <h1 class="page-title">Movie</h1>
                <img v-bind:src="data.image"  class="img-fluid img-movie" v-bind:alt="data">
                  <div>
                      <h1> {{data.title1}}</h1>
            <h2>Rating</h2><fieldset class="rating" >
              <input type="radio" id="star5" name="rating" value="5" /><label
                class="full"
                for="star5"
                title="Awesome - 5 stars"
              ></label>
              <input
                type="radio"
                id="star4half"
                name="rating"
                value="4 and a half"
              /><label
                class="half"
                for="star4half"
                title="Pretty good - 4.5 stars"
              ></label>
              <input
                type="radio"
                id="star4"
                name="rating"
                value="4"
                checked
              /><label
                class="full"
                for="star4"
                title="Pretty good - 4 stars"
              ></label>
              <input
                type="radio"
                id="star3half"
                name="rating"
                value="3 and a half"
              /><label
                class="half"
                for="star3half"
                title="Meh - 3.5 stars"
              ></label>
              <input type="radio" id="star3" name="rating" value="3" /><label
                class="full"
                for="star3"
                title="Meh - 3 stars"
              ></label>
              <input
                type="radio"
                id="star2half"
                name="rating"
                value="2 and a half"
              /><label
                class="half"
                for="star2half"
                title="Kinda bad - 2.5 stars"
              ></label>
              <input type="radio" id="star2" name="rating" value="2" /><label
                class="full"
                for="star2"
                title="Kinda bad - 2 stars"
              ></label>
              <input
                type="radio"
                id="star1half"
                name="rating"
                value="1 and a half"
              /><label
                class="half"
                for="star1half"
                title="Meh - 1.5 stars"
              ></label>
              <input type="radio" id="star1" name="rating" value="1" /><label
                class="full"
                for="star1"
                title="Sucks big time - 1 star"
              ></label>
              <input
                type="radio"
                id="starhalf"
                name="rating"
                value="half"
              /><label
                class="half"
                for="starhalf"
                title="Sucks big time - 0.5 stars"
              ></label>
            </fieldset>
            <br>
                      <h3>{{data.duration}} || {{data.age}}</h3>
                      <h3>{{data.genre1}} | {{data.genre2}} | {{data.genre3}} </h3>
                      <h3>Sutradara : {{data.director}}</h3>
                      <h2> Sinopsis : </h2>
                          <h3 class="desc">
                            {{data.deskripsi}}
                          </h3>

                  </div>
            </div>
        </div>
        <div class="back">
            <router-link to='/'><button class="btn-back">Kembali</button></router-link>
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


export default {
  data() {
    return {
      filmId: this.$route.params.id,
      movie: [
        {
          id: 1,
          image: Img1,
          title1: 'Habibie & Ainun 3',
          duration: '121 Menit',
          age: 'Semua Umur',
          genre1: 'Biography',
          genre2: 'Drama',
          genre3: 'Romance',
          director: 'Hanung Bramantyo',
          deskripsi: 'Habibie & Ainun 3 adalah film biografi percintaan Indonesia tahun 2019 yang disutradarai Hanung Bramantyo dan ditulis Ifan Ismail. Film ini adalah kelanjutan dari Rudy Habibie (2016), prekuel dari Habibie & Ainun, sekaligus film ketiga dari seri Habibie & Ainun. Apabila Rudy Habibie mengisahkan Habibie muda, maka Habibie & Ainun 3 mengisahkan Ainun muda. Maudy Ayunda tampil sebagai pemeran utama, Reza Rahadian kembali membintangi film ini, dan Jefri Nichol bergabung sebagai pemeran baru dalam seri ini. Film ini ditayangkan pada 19 Desember 2019 di Indonesia dan 26 Desember 2019 di Malaysia. Film ini mendapatkan sambutan yang positif baik dari kalangan penonton maupun pengkritik. ',
        },
        {
          id: 2,
          image: Img2,
          title1: 'END GAME',
          duration: '181 Menit',
          age: '17 +',
          genre1: 'Fantasi',
          genre2: 'Action',
          genre3: 'Ilmiah',
          director: 'Anthony Russo, Joe Russo',
          deskripsi: 'Avengers: Endgame adalah film pahlawan super Amerika 2019 yang didasarkan pada Marvel Comics tim superhero the Avengers, diproduksi oleh Marvel Studios dan didistribusikan oleh Walt Disney Studios Motion Pictures. Ini adalah sekuel The Avengers 2012, film 2015 Avengers: Age of Ultron dan film 2018 Avengers: Infinity War, dan film kedua puluh dua di Marvel Cinematic Universe (MCU). Film ini disutradarai oleh Anthony dan Joe Russo, yang ditulis oleh Christopher Markus dan Stephen McFeely, dan menampilkan pemeran ansambel termasuk Robert Downey Jr, Chris Evans, Mark Ruffalo, Chris Hemsworth, Scarlett Johansson, Jeremy Renner, Don Cheadle, Don Cheadle, Paul Rudd, Brie Larson, Karen Gillan, Danai Gurira, Benedict Wong, Jon Favreau, Bradley Cooper, Gwyneth Paltrow, dan Josh Brolin. Dalam film itu, anggota Avengers yang masih hidup dan sekutu mereka berusaha untuk membalikkan kerusakan yang disebabkan oleh Thanos dalam Infinity War. ',
        },
        {
          id: 3,
          image: Img3,
          title1: 'PARASITE',
          duration: '132 Menit',
          age: '17 +',
          genre1: 'Comedy',
          genre2: 'Drama',
          genre3: 'Thriller',
          director: 'Bong Joon Ho',
          deskripsi: 'Keluarga Ki-taek beranggotakan empat orang pengangguran dengan masa depan suram menanti mereka. Suatu hari Ki-woo anak laki-laki tertua direkomendasikan oleh sahabatnya yang merupakan seorang mahasiswa dari universitas bergengsi agar Ki-woo menjadi guru les yang dibayar mahal dan membuka secercah harapan penghasilan tetap. Dengan penuh restu serta harapan besar dari keluarga, Ki-woo menuju ke rumah keluarga Park untuk wawancara. Setibanya di rumah Mr. Park pemilik perusahaan IT global, Ki-woo bertemu dengan Yeon-kyo, wanita muda yang cantik di rumah itu. Setelah pertemuan itu, serangkaian kejadian dimulai.',
        },
      ],
    };
  },
};
</script>
<style scoped>
    .container {
        width: auto;
    }
    .header {
        padding: 50px;
        grid-column: 1/5;
        background-color: black;
        color: #fff;
        text-align: left;
    }
    .header-title {
      font-family: monospace;
      font-size: 70px;
      color: gold;
    }
    .header-subtitle {
      font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
      font-size: 20px;
    }
    .movie-item {
        padding: 50px;
        width: auto;
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        grid-auto-rows: minmax(50px, auto);
        text-align: left;
        background-color: #ededed;
    }
    .page-title {
        grid-column: 1/3;
        text-align: center;
        padding-bottom: 30px;
        background-color: #ededed;
        color: black;
        font-family: 'Times New Roman', Times, serif;
        font-size: 500%;
    }
    .back {
      text-align: center;
      padding-bottom: 50px;
      background-color: #ededed;
    }
    .btn-back {
        background-color: black;
        color: #fff;
        border: 0px;
        border-radius: 60px;
        text-align: center;
        margin: 5px 2px;
        padding: 20px 15px;
        cursor: pointer;
        transition: 0.3s;
        margin: 20px;
        width: 300px;
    }
    .btn-back:hover {
        background-color: transparent;
        border: 2px solid #cfc20e;
        color: #cfc20e;
    }
    .img-movie {
        width: 410px;
        box-shadow: 0 20px 25px 0 rgba(0,0,0,0.2);
        transition: 0.3s ease;
    }
    .desc {
        text-align: justify;
    }
    .footer {
        padding: 10px;
        grid-column: 1/5;
        background-color: #404040;
        color: #fff;
        text-align: center;
    }
</style>

<style>
@import url(https://fonts.googleapis.com/css?family=Lato:400,300,700);

@import url(//netdna.bootstrapcdn.com/font-awesome/3.2.1/css/font-awesome.css);

:after {
  box-sizing: border-box;
}

body {
  background: #43423e;
}

a {
  text-decoration: none;
  color: #5c7fb8;
}

a:hover {
  text-decoration: underline;
}

.movie-card {
  font: 14px/22px "Lato", Arial, sans-serif;
  color: #a9a8a3;
  padding: 40px 0;
}

.container {
  margin: 0 auto;
  width: 780px;
  height: 640px;
  background: #f0f0ed;
  border-radius: 5px;
  position: relative;
}

.hero {
  height: 342px;
  margin: 0;
  position: relative;
  overflow: hidden;
  z-index: 1;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
}

.hero:before {
  content: "";
  width: 100%;
  height: 100%;
  position: absolute;
  overflow: hidden;
  top: 0;
  left: 0;
  background: red;
  background: url("https://s3-us-west-2.amazonaws.com/s.cdpn.io/195612/hobbit_bg.jpg");
  z-index: -1;

  transform: skewY(-2.2deg);
  transform-origin: 0 0;

  -webkit-backface-visibility: hidden;
}

.cover {
  position: absolute;
  top: 160px;
  left: 40px;
  z-index: 2;
}

.details {
  padding: 190px 0 0 280px;
}
.title1 {
  color: white;
  font-size: 44px;
  margin-bottom: 13px;
  position: relative;
}
span {
  position: absolute;
  top: 3px;
  margin-left: 12px;
  background: #c4af3d;
  border-radius: 5px;
  color: #544c21;
  font-size: 14px;
  padding: 0px 4px;
}

.title2 {
  color: #c7c1ba;
  font-size: 23px;
  font-weight: 300;
  margin-bottom: 15px;
}

.likes {
  margin-left: 24px;
}

.likes:before {
  content: url("https://s3-us-west-2.amazonaws.com/s.cdpn.io/195612/icon_like.png");
  position: relative;
  top: 2px;
  padding-right: 7px;
}

.description {
  bottom: 0px;
  height: 200px;
  font-size: 16px;
  line-height: 26px;
  color: #b1b0ac;
}

.column1 {
  padding-left: 50px;
  padding-top: 120px;
  width: 220px;
  float: left;
  text-align: center;
}

.tag {
  background: white;
  border-radius: 10px;
  padding: 3px 8px;
  font-size: 14px;
  margin-right: 4px;
  line-height: 35px;
  cursor: pointer;
}

.tag:hover {
  background: #ddd;
}

.column2 {
  padding-left: 41px;
  padding-top: 30px;
  margin-left: 20px;
  width: 480px;
  float: left;
}

.avatars {
  margin-top: 23px;
}
img {
  cursor: pointer;
}

img:hover {
  opacity: 0.6;
}

a:hover {
  text-decoration: none;
}
fieldset,
label {
  margin: 0;
  padding: 0;
}

/****** Style Star Rating Widget *****/

.rating {
  border: none;
  float: left;
}

.rating > input {
  display: none;
}
.rating > label:before {
  margin: 5px;
  margin-top: 0;
  font-size: 1em;
  font-family: FontAwesome;
  display: inline-block;
  content: "\f005";
}

.rating > .half:before {
  content: "\f089";
  position: absolute;
}

.rating > label {
  color: #ddd;
  float: right;
}

/***** CSS Magic to Highlight Stars on Hover *****/

.rating > input:checked ~ label, /* show gold star when clicked */
.rating:not(:checked) > label:hover, /* hover current star */
.rating:not(:checked) > label:hover ~ label {
  color: #ffd700;
} /* hover previous stars in list */

.rating > input:checked + label:hover, /* hover current star when changing rating */
.rating > input:checked ~ label:hover,
.rating > label:hover ~ input:checked ~ label, /* lighten current selection */
.rating > input:checked ~ label:hover ~ label {
  color: #ffed85;
}

/* //tooltip stuff via: https://codepen.io/peiche/pen/JaftA */

a[data-tooltip] {
  position: relative;
}
a[data-tooltip]::before,
a[data-tooltip]::after {
  position: absolute;
  display: none;
  opacity: 0.85;
}
a[data-tooltip]::before {
  /*
   * using data-tooltip instead of title so we
   * don't have the real tooltip overlapping
   */
  content: attr(data-tooltip);
  background: #000;
  color: #fff;
  font-size: 13px;
  padding: 5px;
  border-radius: 5px;
  /* we don't want the text to wrap */
  white-space: nowrap;
  text-decoration: none;
}
a[data-tooltip]::after {
  width: 0;
  height: 0;
  border: 6px solid transparent;
  content: "";
}

a[data-tooltip]:hover::before,
a[data-tooltip]:hover::after {
  display: block;
}

/** positioning **/

/* top tooltip */
a[data-tooltip][data-placement="top"]::before {
  bottom: 100%;
  left: 0;
  margin-bottom: 40px;
}
a[data-tooltip][data-placement="top"]::after {
  border-top-color: #000;
  border-bottom: none;
  bottom: 50px;
  left: 20px;
  margin-bottom: 4px;
}
</style>
