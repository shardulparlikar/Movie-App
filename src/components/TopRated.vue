<template>
<div class="container heading ">
    <h1>Top Rated Movies </h1>
</div>
  <div class="container">
 
      
        <NewCard
          v-for="data in topRatedData"
          :key="data.id"
          :title="data.title"
          :rating="data.vote_average"
          :date="data.release_date"
          :imageUrl="data.poster_path"
          :language="data.original_language"
          
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
      topRatedData: [],
    };
  },
  props: ["myName"],
  beforeMount() {
    fetch(
      `https://api.themoviedb.org/3/movie/top_rated?api_key=2d7de0ce3660736fec38698dfd88c018`
    )
      .then((response) => {
        if (response.ok) {
          return response.json();
        }
      })
      .then((data) => {
        this.topRatedData = data.results;
       
      });
  },
};

</script>

<style scoped>
.container {
  display: flex;
  max-width: 1366px;
  margin: 0 auto;
  overflow-x: scroll;
  overflow-y: hidden ;
  scroll-behavior: smooth;
}
 h1 {
  font-size:34px; font-weight:500; text-transform:uppercase;
}
 h1:before {
    background-color: #c50000;
    border-radius: 0.25rem;
    content: '';
    display: block;
    height: 0.25rem;
    width: 42px;
    margin-bottom: 1.25rem;
}
</style>