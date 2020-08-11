<template>
  <div class="jumbotron jumbotron-fluid jumbotron-colour">
    <div class="container">
      <h1 class="display-4">Second Fluid jumbotron</h1>
      <p class="lead">
        This is a modified jumbotron that occupies the entire horizontal space of its parent.
      </p>

      <!-- <b-container class="bv-example-row">
        <b-row align-h="center">
          <b-col md="8" offset-md="2" sm="12" align-h="end"> -->
      <div class="grid-container">
        <div class="grid-item-back-top-left">
          <img src="http://placeimg.com/640/360/any" class="back-img-dimensions" />
        </div>
        <div class="grid-item-front-bottom-right">
          <img src="https://dummyimage.com/640x360/fff/aaa" class="front-img-dimensions" />
        </div>
      </div>
      <!-- </b-col>
          <b-col md="2">Three of three columns</b-col>
        </b-row>
      </b-container> -->
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

const stackedBoxes = Vue.extend({
  name: 'stacked-boxes' as string,
  data() {
    const counter = 0;
    return { counter };
  },
});

export default stackedBoxes;
</script>

<style scoped>
.jumbotron {
  margin-bottom: none !important;
}

/* Large devices (laptops/desktops, 992px  and DOWN) */
@media only screen and (max-width: 992px) {
  .back-img-dimensions {
    width: 100%;
    height: auto;
  }

  .front-img-dimensions {
    width: 100%;
    height: 100%;
  }

  .grid-item-back-top-left {
    left: 0px;
  }

  .grid-item-front-bottom-right {
    top: 0px;
  }

  .grid-container {
    min-height: auto;
  }
}

/* Large devices (laptops/desktops, 992px and up) */
@media only screen and (min-width: 992px) {
  .back-img-dimensions {
    width: 766px;
    height: 500px;
  }

  .front-img-dimensions {
    width: 600px;
    height: 500px;
  }

  .grid-item-back-top-left {
    left: 15px;
    grid-area: 1 / 1 / 2 / 2;
  }

  .grid-item-front-bottom-right {
    top: 100px;
    grid-area: 1 / 1 / 2 / 2;
    margin-left: auto;
    margin-right: 0;
  }

  .grid-container {
    min-height: 500px;
  }
}

.jumbotron-colour {
  background-color: whitesmoke !important;
}

.b-col {
  border: 1px solid #000;
}

.grid-container {
  position: static;
  display: grid;
  height: auto;
  width: 100%;
  grid-template-rows: min-content;
  grid-template-columns: 100%;
  padding-bottom: 0px;
  box-sizing: border-box;
}

.grid-item-back-top-left {
  position: relative;
  justify-self: start;
  align-self: start;
}

.grid-item-front-bottom-right {
  position: relative;
  justify-self: start;
  align-self: start;
}
</style>
