<template>
  <div class="container">
    <div class="container-inner">
      <div class="main-content">
        <div class="main-headings" id="main-headings-js">
        <p id="by-line" class="normalfont">{{$route.params.movie.title}}</p>

        <div class="heading">
          <h2 id="heading1"
          class="normalfont">{{ $route.params.movie.release_date }}</h2>
          <span id="heading2"
          v-for="(genre, idx) in genre_list"
          :key="idx">{{ genre.name }}/</span><br>
          <span style="font-size: 500%">⭐</span>
          <span id="heading3">{{ $route.params.movie.vote_average }}</span>
        </div>

        <!-- <div class="short-bio">
          <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Tempore, repellat, quod sed optio nesciunt aspernatur inventore ab, nostrum accusantium harum dolor voluptate nulla!</p>
    
        </div> -->
        <a href="#" class="link" @click="readMore()">SHOW OVERVIEW</a>
        </div>
        
        <div class="more-info" id="more-info-js">
          <br>
          <br>
          
          <p class="normalfont">{{ $route.params.movie.overview }}</p>
          
        </div>
        
        </div>

        <div class="image-wrapper">
        <div class="image-container">
          <img class="image" :src="`https://www.themoviedb.org/t/p/w1280/${$route.params.movie.poster_path}`">
        </div>
      </div>
        <b-button class="btncl" @click="GoSummer" variant="light">BACK</b-button>
        
    </div>
  </div>
</template>


<script>
import { readMore } from '@/assets/js/detail.js'

export default {
  name: 'MovieDetail',
  props: {
    movie: Object,
  },
  data: function () {
    return {
      genre_list: this.movie.genre_ids,
      readMore,
    }
  },
  methods: {
    GoSummer: function () {
      this.$router.push('/summer')
    },
  }
}
</script>

<style scoped>
/* div {
    display: block;
    margin-left: auto;
    margin-right: auto } */
.btncl {
    background-color: #8AB6D6;
    color: white;
    border: none;
}
.normalfont {
  font-family: DX시인과나;
  font-style: initial;
  color:black;
  font-weight: bold;
  text-overflow: ellipsis;
}

@import url("https://fonts.googleapis.com/css?family=Montserrat:400,700");
@keyframes fade-in {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes slide-in {
  0% {
    top: -300px;
  }
  100% {
    top: 0;
  }
}
@keyframes scaleDown {
  0% {
    transform: scale(1);
  }
  10% {
    transform: scale(0.7);
  }
  95% {
    transform: scale(0.7);
  }
  100% {
    transform: scale(1);
  }
}
@keyframes reveal-info {
  0% {
    height: 0;
  }
  5% {
    height: 350px;
  }
  95% {
    height: 350px;
  }
  100% {
    height: 0;
  }
}
body {
  margin: 0;
  padding: 0;
}

.container {
  margin-top: 50px;
  margin-left: auto;
  margin-right: auto;
  width: 1200px;
  height: 700px;
  background-color: #FBE0C4;
  font-size: 13.8px;
  font-family: "Montserrat", sans;
}
.container .container-inner {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  position: relative;
  animation: fade-in 1.5s ease, slide-in 1.2s ease;
  -webkit-animation: fade-in 1.5s ease, slide-in 1.2s ease;
}
.container .container-inner .main-content {
  flex-basis: 50%;
  order: 1;
  align-self: center;
  display: flex;
  flex-direction: column;
}
.container .container-inner .main-content .main-headings {
  width: 100%;
  align-self: center;
  display: flex;
  flex-direction: column;
  animation: scaleDown 6s ease 2s;
  -webkit-animation: scaleDown 6s ease 2s;
}
.container .container-inner .main-content .main-headings #by-line {
  width: 100%;
  padding-bottom: 1px;
  padding-left: 3px;
  margin-left: 75px;
  font-size: 285%;
  border-bottom: 1px solid #757575;
}
.container .container-inner .main-content .main-headings .heading {
  margin-top: 20px;
  margin-left: 80px;
}
.container .container-inner .main-content .main-headings .heading #heading1, .container .container-inner .main-content .main-headings .heading #heading2, .container .container-inner .main-content .main-headings .heading #heading3 {
  margin: 0;
  margin-top: -20px;
}
.container .container-inner .main-content .main-headings .heading #heading1, .container .container-inner .main-content .main-headings .heading #heading2 {
  font-size: 200%;
  font-weight: normal;
  letter-spacing: -2px;
}
.container .container-inner .main-content .main-headings .heading #heading1 {
  /* margin-left: 50px; */
}
.container .container-inner .main-content .main-headings .heading #heading2 {
  /* margin-left: 150px; */
}
.container .container-inner .main-content .main-headings .heading #heading3 {
  /* margin-top: -52px; */
  font-size: 500%;
  font-weight: 600;
  letter-spacing: 2px;
}
.container .container-inner .main-content .main-headings .short-bio {
  width: 60%;
  margin-top: -30px;
  margin-left: 90px;
  font-style: italic;
  font-size: 105%;
}
.container .container-inner .main-content .main-headings a {
  margin-left: 200px;
  align-self: flex-start;
  font-weight: bold;
  font-size: 120%;
  font-family: helvetica;
  text-decoration: none;
  color: black;
}
.container .container-inner .main-content .main-headings a:hover {
  text-decoration: underline;
}
.container .container-inner .main-content .more-info {
  margin-top: -70px;
  width: 50%;
  height: 0;
  margin-left: auto;
  margin-right: auto;
  align-self: flex-start;
  overflow: hidden;
  animation: reveal-info 4s ease 3s;
  -webkit-animation: reveal-info 4s ease 3s;
}
.container .container-inner .image-wrapper {
  flex-basis: 50%;
  order: 2;
}
.container .container-inner .image-wrapper .image-container {
  width: 100%;
  height: 100%;
  overflow: hidden;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  animation: scaleDown 6s ease 2s;
  -webkit-animation: scaleDown 6s ease 2s;
}
.container .container-inner .image-wrapper .image-container img {
  width: 100%;
  height: auto;
  position: relative;
}

@media (min-width: 350px) and (max-width: 529px) {
  * {
    animation-name: none !important;
  }

  .container {
    width: 90%;
    height: 700px;
    margin-left: auto;
    margin-right: auto;
    font-size: 5px;
    margin-bottom: 20px;
  }

  .container-inner {
    flex-direction: column !important;
    justify-content: center !important;
  }

  .main-content, .image-wrapper {
    flex-basis: 100% !important;
  }

  .main-content {
    order: 2 !important;
    outline: 1px solid red;
    margin: 0 50px;
  }

  .image-wrapper {
    order: 1 !important;
  }

  .heading {
    margin-left: 55px !important;
  }

  #heading1, #heading2 {
    margin: 0;
    margin-top: -5px !important;
  }

  #heading2 {
    margin-left: 100px !important;
  }

  #heading3 {
    margin-top: -20px !important;
  }

  .short-bio {
    margin-top: -10px !important;
    margin-left: 60px !important;
  }

  .more-info {
    height: 150px !important;
    width: 60% !important;
    margin: 0 !important;
    align-self: flex-start !important;
    margin-top: 0px !important;
    margin-left: 60px !important;
    font-size: 8px;
  }

  .link {
    display: none;
  }

  .image-wrapper {
    order: 1 !important;
    width: 100%;
    height: 100px !important;
    justify-content: center !important;
  }

  .image-container {
    width: 100% !important;
    height: 400px;
    margin-left: auto;
    margin-right: auto;
    position: relative;
    top: 50%;
    transform: translateY(-50%);
  }

  img {
    width: 80% !important;
    height: auto !important;
    top: -20px;
    margin-left: auto;
    margin-right: auto;
  }
}
@media (min-width: 530px) and (max-width: 699px) {
  * {
    animation-name: none !important;
  }

  .container {
    width: 90%;
    height: 900px;
    margin-left: auto;
    margin-right: auto;
    font-size: 8px;
  }

  .container-inner {
    flex-direction: column !important;
    justify-content: center !important;
  }

  .main-content, .image-wrapper {
    flex-basis: 100% !important;
  }

  .main-content {
    width: 80%;
    order: 2 !important;
    align-self: center !important;
  }

  .main-headings {
    width: 100%;
    margin-top: 20px;
    margin-left: auto;
    margin-right: auto;
  }

  .heading {
    margin-left: 55px !important;
  }

  #heading1, #heading2 {
    margin: 0;
    margin-top: -15px !important;
  }

  #heading3 {
    margin-top: -30px !important;
  }

  .short-bio {
    margin-top: -20px !important;
    margin-left: 60px !important;
  }

  .link {
    display: none;
  }

  .more-info {
    height: 150px !important;
    width: 60% !important;
    margin: 0 !important;
    align-self: flex-start !important;
    margin-top: 0px !important;
    margin-left: 60px !important;
    text-align: justify;
  }

  .image-wrapper {
    order: 1 !important;
    width: 100%;
    height: 400px;
    justify-content: center !important;
  }

  .image-container {
    width: 100% !important;
    height: 400px;
    margin-left: auto;
    margin-right: auto;
  }

  img {
    width: 80% !important;
    height: auto !important;
    top: -20px;
    margin-left: auto;
    margin-right: auto;
  }
}
/*

@include tablet {
  .container {
    width: 100%;
    height: auto;
    font-size: 7px;
  }
  #heading3 {
    margin-top: -35px !important;
  }
  .link {
    margin-left: 30px;
  }
  .more-info {
    margin-top: -40px !important;
  }
}
*/
@media (min-width: 700px) and (max-width: 1200px) {
  .container {
    width: 100%;
    height: auto;
    font-size: 9px;
  }

  #heading3 {
    margin-top: -35px !important;
  }

  .link {
    margin-left: 30px;
  }

  .more-info {
    margin-top: -40px !important;
  }
}
</style>
