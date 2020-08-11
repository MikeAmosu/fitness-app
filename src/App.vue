<template>
  <div id="app">
    <ul class="nav justify-content-end">
      <li class="nav-item">
        <router-link class="nav-link active" to="/">Home</router-link>
      </li>
      <li class="nav-item">
        <router-link to="/about" class="nav-link">Payment</router-link>
      </li>
      <li class="nav-item">
        <a href="#" class="nav-link">Get Started</a>
      </li>
    </ul>
    <router-view />
  </div>
</template>

<script lang="ts">
import 'bootstrap/dist/css/bootstrap.css';
import 'bootstrap-vue/dist/bootstrap-vue.css';

import Vue from 'vue';

export default Vue.extend({
  name: 'App' as string,
});
</script>

<style lang="scss">
// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
// }

// #nav {
//   padding: 30px;

//   a {
//     font-weight: bold;
//     color: #2c3e50;

//     &.router-link-exact-active {
//       color: #42b983;
//     }
//   }
// }
</style>
