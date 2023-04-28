<template>
  <div class="bg-white col-xs-2 flex flex-center" style="height: 35px">
    <div class="hover-blue" style="font-weight: bold">
      {{ item.title }}
      <q-menu fit transition-show="flip-right" transition-hide="flip-left">
        <q-list>
          <CompoMenuItem
            v-for="(item, index) in item.suptitle"
            v-bind:key="index"
            clickable
            v-close-popup
            v-bind:item="item"
          />
        </q-list>
      </q-menu>
      <q-icon name="expand_more" />
    </div>
  </div>
</template>

<script>
import CompoMenuItem from "./CompoMenuItem.vue";

export default {
  setup() {
    return {
      menu_cat_elc: false,
    };
  },
  components: {
    CompoMenuItem,
  },
  props: {
    item: Object,
  },
};
</script>

<style>
.hover-blue {
  color: #000;
}
.hover-blue:hover {
  color: #1f509e;
}
</style>
