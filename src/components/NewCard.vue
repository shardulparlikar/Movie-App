<template>
  <div class="card">
    <div class="card-image">

        <img :src="`https://www.themoviedb.org/t/p/w220_and_h330_face/${imageUrl}`" alt="">
    </div>
    <div class="card-name">
        <h3>{{title}}</h3>
    </div>
    <div class="card-rating">
        <p>{{rating}}</p>
    </div>
    <div class="card-date">
      <p>{{date}}</p>
    </div>
    <div class="card-language">

        <p>{{isotodate(language)}} </p>

    </div>


  </div>

</template>

<script>

import ISO6391 from 'iso-639-1';

export default {
  components :{
  }
  ,
props: ["title",
'rating',
'date',
'imageUrl',
'language'],
methods: {
  isotodate : function (languageCode){
    return ISO6391.getName(languageCode)
  }
}
}

</script>

<style>
@font-face {
  font-family: 'Poppins';
  src: url('../assets/fonts/Poppins-Regular.ttf');
}
body{
  font-family: Poppins;
  background-color: darkslategray;
}
.card{
        border-radius: 12px;
    box-shadow: 0 2px 8px rgb(0 0 0 / 26%);
    padding: 1rem 2rem;
    margin: 1rem;
    max-width: 240px;
    background-color: #fff;
    flex: 0 0 30%;
  
}
.card-name h3 {
  font-size: 20px;
  font-weight: 100;
    color: rgb(0, 0, 0);
}

.card-rating{
  background-color: lightgrey;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.card-rating p {
  color: rgb(1, 110, 1);
  font-weight: bolder;
}
.card-image img{
  max-width: 100%;
  object-fit: contain;
  max-height: 250px;
  width: 100%;

}

</style>