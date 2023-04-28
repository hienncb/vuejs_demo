<template>
  <q-header class="bg-primary">
    <q-toolbar>
      <q-toolbar-title>
        <q-btn flat v-on:click="drawerLeft" round dense icon="menu" />
        <span>Shoppe</span>
      </q-toolbar-title>

      <div>
        <q-input
          class="float-left q-mx-md full-width"
          square
          bg-color="white"
          dense
          outlined
          v-model="textInput"
          label="Search for products, brands and more"
        />
      </div>

      <div>
        <q-btn class="q-mr-md" dense round flat icon="shopping_cart">
          <q-badge color="red" class="text-bold" floating transparent>
            4
          </q-badge>
        </q-btn>
        <q-btn flat round dense icon="settings" class="q-mr-md" />
        <q-btn flat round dense icon="logout" to="/" />
      </div>
    </q-toolbar>
    <div>
      <CompoMenuIndexVue />
    </div>
  </q-header>
</template>
<script>
import CompoMenuIndexVue from "./menu/CompoMenuIndex.vue";

export default {
  name: "compo-head",
  data() {
    return {
      textInput: "",
    };
  },
  components: {
    CompoMenuIndexVue,
  },
  props: {
    showMenu: {
      isShowDraw: Boolean,
      default: false,
    },
  },
  methods: {
    drawerLeft(data) {
      var value = data;
      this.$emit("handeShowDrawMenu", { value });
    },
  },
};
</script>

<style>
</style>
