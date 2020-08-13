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
          <img src="http://placeimg.com/640/360/any" class="img-dimensions" />
        </div>
        <!-- <div class="grid-bottom"></div> -->
        <div class="grid-item-front-bottom-right info-box"></div>
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
  .grid-item-front-bottom-right {
    min-height: 200px;
  }

  .grid-container {
    grid-template-columns: 1f;
    grid-template-rows: minmax(0, 1fr);
    min-height: auto;
  }
}

/* Large devices (laptops/desktops, 992px and up) */
@media only screen and (min-width: 992px) {
  .grid-item-back-top-left {
    grid-column: 1 / 10;
    grid-row: 1 / 4;
  }

  .grid-item-front-bottom-right {
    grid-column: 7 / 13;
    grid-row: 2 / 5;
  }

  .grid-container {
    min-height: 500px;
    grid-template-columns: repeat(12, 1fr);
    grid-template-rows: 1fr 1fr 1fr auto;
  }
}

.img-dimensions {
  width: 100%;
  height: auto;
}

.jumbotron-colour {
  background-color: whitesmoke !important;
}

.b-col {
  border: 1px solid #000;
}

.grid-container {
  display: grid;
  width: 100%;
  padding-bottom: 0px;
  box-sizing: border-box;
}

.grid-item-back-top-left {
  /* position: relative;
  justify-self: start;
  align-self: start; */
}

.grid-item-front-bottom-right {
  /* position: relative; */
  /* justify-self: start;
  align-self: start; */
}

.grid-bottom {
  height: 50px;
}

.info-box {
  background-color: aquamarine;
  border: 1px solid darkblue;
}
</style>
