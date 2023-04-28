<template>
  <q-drawer v-model="drawState" :width="200" :breakpoint="700" bordered>
    <q-scroll-area class="fit">
      <CompoAccountInfo />
      <q-separator />
      <CompoDrawItem
        padding
        class="menu-list"
        v-for="(item, index) in drawValue"
        v-bind:key="index"
        v-bind:item="item"
      />
    </q-scroll-area>
  </q-drawer>
</template>

<script>
import CompoAccountInfo from "./CompoAccountInfo.vue";
import CompoDrawItem from "./CompoDrawItem.vue";

const drawValue = [
  {
    accountName: "inbox",
    image: "inbox",
  },
  {
    accountName: "star",
    image: "star",
  },
  {
    accountName: "send",
    image: "send",
  },
  {
    accountName: "drafts",
    image: "drafts",
  },
  {
    accountName: "out",
    image: "logout",
  },
];

export default {
  setup() {
    return {
      drawValue: drawValue,
    };
  },
  props: {
    showDraw: Boolean,
  },
  components: {
    CompoAccountInfo,
    CompoDrawItem,
  },
  computed: {
    drawState: {
      get() {
        return this.showDraw;
      },
    },
  },
};
</script>

<style>
.menu-list {
  border-radius: 0 32px 32px 0;
}
</style>
