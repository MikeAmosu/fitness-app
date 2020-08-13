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
      <div class="grid-container" :class="gridContainerSelection">
        <div :class="gridItemSelection.back">
          <div class="parallax"></div>
          <!-- <img src="http://placeimg.com/640/360/any" class="img-dimensions" /> -->
        </div>
        <!-- <div class="grid-bottom"></div> -->
        <div :class="gridItemSelection.front" class="info-box" v-html="message"></div>
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

interface ILayout {
  front: string;
  back: string;
}

const stackedBoxes = Vue.extend({
  name: 'stacked-boxes' as string,
  data() {
    const counter = 0;
    const message = `<h2>Hi, I’m Sheldon</h2>
<h3>Certified Fitness Trainer and Personal Coach</h3>
 <br>
<p>I'm a paragraph. Click here to add your own text and edit me. \
It’s easy. Just click “Edit Text” or double click me to add your \
own content and make changes to the font. I’m a great place for you \
to tell a story and let your users know a little more about you.</p>
<br>
<p>I'm a paragraph. Click here to add your own text and edit me. \
It’s easy. Just click “Edit Text” or double click me to add your \
own content and make changes to the font. I’m a great place for you \
to tell a story and let your users know a little more about you.</p>`;

    const layout = {
      topLeft: 'top-left',
      topRight: 'top-right',
      bottomLeft: 'bottom-left',
      bottomRight: 'bottom-right',
    };
    const layoutSelection = layout.bottomRight;

    return {
      counter,
      message,
      layoutSelection,
      layout,
    };
  },
  computed: {
    gridItemSelection(): ILayout {
      const gridPrefix = 'grid-item';
      const defaultLayout: ILayout = {
        front: `${gridPrefix}-front-${this.layout.bottomRight}`,
        back: `${gridPrefix}-back-${this.layout.topLeft}`,
      };

      if (!this.layoutSelection) {
        return defaultLayout;
      }

      if (this.layoutSelection === this.layout.topLeft) {
        return {
          front: `${gridPrefix}-front-${this.layout.topLeft}`,
          back: `${gridPrefix}-back-${this.layout.bottomRight}`,
        };
      }
      if (this.layoutSelection === this.layout.topRight) {
        return {
          front: `${gridPrefix}-front-${this.layout.topRight}`,
          back: `${gridPrefix}-back-${this.layout.bottomLeft}`,
        };
      }
      if (this.layoutSelection === this.layout.bottomLeft) {
        return {
          front: `${gridPrefix}-front-${this.layout.bottomLeft}`,
          back: `${gridPrefix}-back-${this.layout.topRight}`,
        };
      }

      return defaultLayout;
    },
    gridContainerSelection(): string {
      const defaultGridContainer = 'grid-container-for-bottom';
      if (!this.layoutSelection || this.layoutSelection.indexOf('bottom') > -1) {
        return defaultGridContainer;
      }

      return 'grid-container-for-top';
    },
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
  .grid-item-back-bottom-right,
  .grid-item-back-bottom-left {
    order: 2;
  }

  .grid-item-front-top-left,
  .grid-item-front-top-right {
    order: 1;
  }

  .grid-container {
    grid-template-columns: 1f;
    min-height: auto;
  }

  .grid-container-for-top,
  .grid-container-for-bottom {
    grid-template-rows: auto auto;
  }

  .parallax {
    background-attachment: scroll;
    width: 100%;
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
    min-height: 400px;
  }

  .grid-item-back-top-right {
    grid-column: 3 / 13;
    grid-row: 1 / 4;
  }

  .grid-item-front-bottom-left {
    grid-column: 1 / 7;
    grid-row: 2 / 5;
    min-height: 400px;
  }

  .grid-item-back-bottom-right {
    grid-column: 3 / 13;
    grid-row: 2 / 5;
  }

  .grid-item-front-top-left {
    grid-column: 1 / 7;
    grid-row: 1 / 4;
    min-height: 400px;
  }

  .grid-item-back-bottom-left {
    grid-column: 1 / 10;
    grid-row: 2 / 5;
  }

  .grid-item-front-top-right {
    grid-column: 7 / 13;
    grid-row: 1 / 4;
    min-height: 400px;
  }

  .grid-container {
    min-height: 500px;
    grid-template-columns: repeat(12, 1fr);
    grid-template-rows: 1fr 1fr 1fr auto;
  }

  .grid-container-for-top {
    grid-template-rows: 1fr 1fr 1fr 1fr;
  }

  .grid-container-for-bottom {
    grid-template-rows: 1fr 1fr 1fr auto;
  }

  .parallax {
    background-attachment: fixed;
    height: 500px;
    width: auto;
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

.grid-bottom {
  height: 50px;
}

.info-box {
  background-color: aquamarine;
  border: 1px solid darkblue;
}

.parallax {
  background-image: url('http://placeimg.com/640/360/any');

  /* Full height */
  min-height: 400px;

  /* Create the parallax scrolling effect */
  /* background-attachment: fixed; */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
