<script setup>

import { onMounted, ref } from 'vue';
import PageLoader from './components/pageLoader.vue';

const isLoading=ref(true)
onMounted(()=>{
  setTimeout(()=>{
    isLoading.value=false;
  }, 12000)
})
</script>

<template>
  <PageLoader v-if="isLoading"></PageLoader>
  <router-view v-if="isLoading==false" />
</template>

<style>
@import url(./assets/index.css);
* {
  margin: 0;
}
#app {
  font-family: montserrat;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* color: #f6aa8c; */
  color: #0c221d;
  background-color: #a6a9b3;
}

nav {
  height: 8vh;
  padding: 1vh 0;
}

nav a {
  font-weight: bold;
  color: #0a1011;
}

nav a.router-link-exact-active {
  color: #0a1011;
}
</style>
