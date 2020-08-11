<template>
  <div class="jumbotron jumbotron-fluid jumbotron-colour">
    <div class="container">
      <h1 class="display-4">Third Fluid jumbotron</h1>
      <p class="lead">
        This is a modified jumbotron that occupies the entire horizontal space of its parent.
      </p>

      <div>
        <b-card-group deck>
          <b-card
            title="Title"
            img-src="https://picsum.photos/300/300/?image=41"
            img-alt="Image"
            img-top
          >
            <b-card-text>
              This is a wider card with supporting text below as a natural lead-in to additional
              content. This content is a little bit longer.
            </b-card-text>
            <template v-slot:footer>
              <small class="text-muted">Last updated 3 mins ago</small>
            </template>
          </b-card>

          <b-card
            title="Title"
            img-src="https://picsum.photos/300/300/?image=41"
            img-alt="Image"
            img-top
          >
            <b-card-text>
              This card has supporting text below as a natural lead-in to additional content.
            </b-card-text>
            <template v-slot:footer>
              <small class="text-muted">Last updated 3 mins ago</small>
            </template>
          </b-card>

          <b-card
            title="Title"
            img-src="https://picsum.photos/300/300/?image=41"
            img-alt="Image"
            img-top
          >
            <b-card-text>
              This is a wider card with supporting text below as a natural lead-in to additional
              content. This card has even longer content than the first to show that equal height
              action.
            </b-card-text>
            <template v-slot:footer>
              <small class="text-muted">Last updated 3 mins ago</small>
            </template>
          </b-card>
        </b-card-group>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'card-container' as string,
  data() {
    const somedata = 123;

    return { somedata };
  },
});
</script>

<style scoped>
.jumbotron {
  margin-bottom: none !important;
}
</style>
