<template>
  <q-item @click="$router.push('/category')" clickable>
    <q-item-section>{{ item }}</q-item-section>
  </q-item>
</template>

<script>
export default {
  setup() {},
  props: {
    item: String,
  },
};
</script>

<style>
.hover_underline_white:hover {
  text-decoration: underline !important;
  cursor: pointer;
}
</style>
