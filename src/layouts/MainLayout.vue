<template>
  <q-layout view="lHh LpR lFf" class="q-layout lightgrey">
    <HeaderIndexVue />

    <q-page-container>
      <router-view />
      <div class="q-mt-sm">
        <FooterIndex />

        <div style="background-color: #163758">
          <div
            class="q-mr-md text-right q-py-xs text-weight-bold text-grey-6"
            style=""
          >
            Made with
            <span style="color: #e25555; font-size: 16px">&#9829;</span> using
            <a
              target="_blank"
              class="text-blue-1 hover_underline_white"
              style="text-decoration: none"
              href="https://quasar-framework.org"
              >&nbsp;Quasar&nbsp;</a
            >
            by
            <a
              target="_blank"
              class="text-blue-1 hover_underline_white"
              style="text-decoration: none"
              >hienncb</a
            >.
          </div>
        </div>
      </div>

      <q-page-scroller position="bottom">
        <q-btn fab icon="keyboard_arrow_up" color="red" />
      </q-page-scroller>
    </q-page-container>
  </q-layout>
</template>

<script>
import FooterIndex from "src/components/footer/FooterIndex.vue";
import { defineComponent, ref } from "vue";
import HeaderIndexVue from "src/components/header/HeaderIndex.vue";

export default defineComponent({
  name: "MainLayout",

  components: {
    FooterIndex,
    HeaderIndexVue,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      drawerLeft: ref(false),
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>

<style>
.q-layout {
  height: 100% !important;
}
</style>
