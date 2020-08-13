<template>
  <div>
    <div class="jumbotron jumbotron-fluid">
      <div class="container">
        <h1 class="display-4">Fluid jumbotron</h1>
        <p class="lead">
          This is a modified jumbotron that occupies the entire horizontal space of its parent.
        </p>
        <carousel />
      </div>
    </div>
    <stackedboxes></stackedboxes>
    <cardcontainer></cardcontainer>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import carousel from './components/carousel.vue';
import stackedboxes from './components/stacked-boxes.vue';
import cardcontainer from './components/card-container.vue';

const home = Vue.extend({
  name: 'home' as string,
  components: {
    carousel,
    stackedboxes,
    cardcontainer,
  },
});
export default home;
</script>

<style lang="scss" scoped>
.jumbotron {
  margin-bottom: 0px !important;
}
</style>
