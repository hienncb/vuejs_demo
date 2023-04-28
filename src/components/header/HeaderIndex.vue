<template>
  <div class="row">
    <CompoHeard
      v-on:handeShowDrawMenu="handeShowDrawMenu"
      v-bind:showDraw="showDraw"
    />
    <CompoDraw v-bind:showDraw="showDraw" />
  </div>
</template>

<script>
import CompoDraw from "../drawer/DrawerIndex.vue";
import CompoHeard from "./compoHead.vue";

export default {
  name: "Header-Index",
  components: {
    CompoHeard,
    CompoDraw,
  },

  data() {
    return {
      showDraw: false,
    };
  },

  methods: {
    handeShowDrawMenu() {
      this.showDraw = this.updateShowDraw;
      console.log(this.showDraw);
    },
  },

  computed: {
    updateShowDraw() {
      return !this.showDraw;
    },
  },
};
</script>

<style>
</style>
