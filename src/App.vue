<template>
  <TopRated />
  <UpComing/>
</template>

<script>
import TopRated from './components/TopRated'
import UpComing   from './components/UpComing'

export default {
  name: 'App',
  components: {
    TopRated,
    UpComing
  },
  
}
</script>

<style>
.container.heading {
  color: aliceblue;
  overflow: hidden;
}
.container::-webkit-scrollbar {
  width: 20px;
}
.container::-webkit-scrollbar-thumb {
  background-color: #d6dee1;
  
  border-radius: 20px;
  border: 6px solid transparent;
  background-clip: content-box;
}
</style>
