<template>
  <div class="row bg-white shadow-6">
    <CompoMenuTitle
      v-for="(item, index) in menu"
      v-bind:key="index"
      v-bind:item="item"
    />
  </div>
</template>

<script>
import CompoMenuTitle from "./CompoMenuTitle.vue";

const dataMenu = [
  {
    title: "Electronics",
    suptitle: [
      "Mobiles",
      "Laptops",
      "Health Care Appliances",
      "Speakers",
      "Smart Home Automation",
    ],
  },
  {
    title: "TVs and Appliances",
    suptitle: [
      "Mobiles",
      "Laptops",
      "Health Care Appliances",
      "Speakers",
      "Smart Home Automation",
    ],
  },
  {
    title: "Man",
    suptitle: [
      "Mobiles",
      "Laptops",
      "Health Care Appliances",
      "Speakers",
      "Smart Home Automation",
    ],
  },
  {
    title: "Woment",
    suptitle: [
      "Mobiles",
      "Laptops",
      "Health Care Appliances",
      "Speakers",
      "Smart Home Automation",
    ],
  },
  {
    title: "Home & Furniture",
    suptitle: [
      "Mobiles",
      "Laptops",
      "Health Care Appliances",
      "Speakers",
      "Smart Home Automation",
    ],
  },
  {
    title: "Other",
    suptitle: [
      "Mobiles",
      "Laptops",
      "Health Care Appliances",
      "Speakers",
      "Smart Home Automation",
    ],
  },
];

export default {
  setup() {
    return {
      menu: dataMenu,
    };
  },
  components: {
    CompoMenuTitle,
  },
};
</script>
