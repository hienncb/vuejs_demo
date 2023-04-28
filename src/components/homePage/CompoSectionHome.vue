<template>
  <div class="section-page shadow-6">
    <div class="row">
      <div class="section-title">Latest Launches</div>
      <div class="section-more">[see all]</div>
    </div>
    <div>
      <q-carousel
        v-model="latest_slide"
        transition-prev="slide-right"
        transition-next="slide-left"
        swipeable
        animated
        control-color="primary"
        navigation
        padding
        arrows
        height="100%"
        class="rounded-borders"
      >
        <q-carousel-slide
          v-for="(val, idx) in [1, 2, 3]"
          :name="val"
          :key="idx"
          class="column no-wrap"
        >
          <div class="row flex justify-center">
            <ComPoSectionItemHomeVue />

            <ComPoSectionItemHomeVue />

            <ComPoSectionItemHomeVue />

            <ComPoSectionItemHomeVue />

            <ComPoSectionItemHomeVue />
          </div>
        </q-carousel-slide>
      </q-carousel>
    </div>
  </div>
</template>

<script>
import ComPoSectionItemHomeVue from "./ComPoSectionItemHome.vue";
import { ref } from "vue";
export default {
  setup() {
    return {
      latest_slide: ref(1),
    };
  },
  components: {
    ComPoSectionItemHomeVue,
  },
};
</script>

<style>
.section-page {
  margin-inline: 15px;
  background: white;
  border-radius: 1px 1px 1px 1px;
  padding: 10px;
}

.section-item {
  margin-left: 1%;
  margin-right: 1%;
}
.section-title {
  margin-top: 0px;
  margin-bottom: 0px;
  font-weight: 600;
  font-size: large;
}
.section-more {
  margin-top: auto;
  margin-bottom: auto;
  margin-left: 10px;
  color: blueviolet;
  font-weight: 500;
}
</style>
