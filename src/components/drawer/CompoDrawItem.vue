<template>
  <q-item clickable v-ripple>
    <q-item-section avatar>
      <q-icon v-bind:name="item.image" />
    </q-item-section>

    <q-item-section class="item-name-section">
      {{ item.accountName }}
    </q-item-section>
  </q-item>
</template>

<script>
export default {
  name: "compo-draw-item",
  props: {
    item: Object,
  },
};
</script>

<style>
.item-name-section {
  font-weight: 400;
}
</style>
