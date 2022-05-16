<template>
  <div id="app">
    <HomeView />
  </div>
</template>

<script>
import HomeView from './views/HomeView.vue'
export default {
  components:{
    HomeView
  },

}
</script>

<style>
body{
  background: #42275a;  /* fallback for old browsers */
background: -webkit-linear-gradient(to right, #734b6d, #42275a);  /* Chrome 10-25, Safari 5.1-6 */
background: linear-gradient(to right, #734b6d, #42275a); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

color: #000000;
}

#app{
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
