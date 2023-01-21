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
  <div class="" v-else>
    <aside>
      <nav>
        <ul>
          <li>
            <a href="#home">Pantheon</a>
          </li>
          <li>
            <a href="#gods">Olympus</a>
          </li>
        </ul>
      </nav>
    </aside>
    <router-view  />
  </div>

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
  transition: 1s all;
}
aside{
  position: fixed;
  width: 10%;
  height: 60%;
  bottom: 30%;
  z-index: 50;
  right:5%
}
li{
  list-style-type: none;
}
nav {
  height: 8vh;
  padding: 1vh 0;
}

nav a {
  font-family: roxette;
  letter-spacing: .5em;
  font-weight: bold;
  color: #121212;
}

nav a.router-link-exact-active {
  color: #0a1011;
}
</style>
