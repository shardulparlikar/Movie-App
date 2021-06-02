<template>
<div class="container heading">
    <h1>Up coming Movies</h1>
</div>
  <div class="container">
 
      
        <NewCard
          v-for="upData in upComingMoiveData"
          :key="upData.id"
          :title="upData.original_title"
          :rating="upData.vote_average"
          :date="upData.release_date"
          :imageUrl="upData.poster_path"
          :language="upData.original_language"
          
        ></NewCard>
      
   
  </div>
</template>

<script>
import NewCard from "./NewCard";
export default {
    components: {
    NewCard,

    
  },
    data() {
        return {
            upComingMoiveData : []
        }
    },
beforeMount(){
  fetch(`https://api.themoviedb.org/3/movie/upcoming?api_key=2d7de0ce3660736fec38698dfd88c018`).then((response)=>{
    if(response.ok){
      return response.json()
    }
  }).then((data)=>{
    this.upComingMoiveData = data.results;
    console.log( this.upComingMoiveData)
  })
}
}
</script>

<style scoped>
.container {
  display: flex;
  max-width: 1366px;
  margin: 0 auto;
  overflow-x: scroll;
  overflow-y: hidden ;
  
}
h1{

}
</style>