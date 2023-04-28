<template>
  <div class="q-pa-md">
    <q-layout view="lHh lpr lFf">
      <q-page-container>
        <CompoSlideIndexVue />
        <CompoSectionHomeVue />
      </q-page-container>
    </q-layout>
  </div>
</template>
<script>
import CompoSlideIndexVue from "src/components/slide/compoSlideIndex.vue";
import CompoSectionHomeVue from "src/components/homePage/CompoSectionHome.vue";

export default {
  components: {
    CompoSlideIndexVue,
    CompoSectionHomeVue,
  },
};
</script>
<style>
</style>
