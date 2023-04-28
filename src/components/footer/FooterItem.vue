<template>
  <div class="text-caption hover_underline_white" v-on:click="gotoLinkFooter">
    {{ item.title }}
  </div>
</template>
<script>
export default {
  name: "footer-item",
  props: {
    item: {
      title: Object,
      default: null,
    },
  },
  data() {
    return {};
  },

  methods: {
    gotoLinkFooter() {
      var title = this.item.title;
      console.log("go to method: " + title);
    },
  },
};
</script>

<style>
.hover_underline_white:hover {
  text-decoration: underline !important;
  cursor: pointer;
}
</style>