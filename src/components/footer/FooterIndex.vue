<template>
  <div class="row q-pa-md bg-primary flex justify-center">
    <div class="col-lg-2 col-md-2 col-sm-12 col-xs-12 text-white">
      <div class="text-subtitle1 text-weight-bold">About</div>
      <FooterItem
        v-for="(item, index) in items1"
        v-bind:key="index"
        v-bind:item="item"
      />
    </div>
    <div class="col-lg-2 col-md-2 col-sm-12 col-xs-12 text-white">
      <div class="text-subtitle1 text-weight-bold">Connect with Us</div>
      <FooterItem
        v-for="(item, index) in items2"
        v-bind:key="index"
        v-bind:item="item"
      />
    </div>
    <div class="col-lg-2 col-md-2 col-sm-12 col-xs-12 text-white">
      <div class="text-subtitle1 text-weight-bold">Policy</div>
      <FooterItem
        v-for="(item, index) in items3"
        v-bind:key="index"
        v-bind:item="item"
      />
    </div>
    <div class="col-lg-2 col-md-2 col-sm-12 col-xs-12 text-white">
      <div class="text-subtitle1 text-weight-bold">Help</div>
      <FooterItem
        v-for="(item, index) in items4"
        v-bind:key="index"
        v-bind:item="item"
      />
    </div>
    <div
      class="text-white"
      :class="$q.platform.is.desktop ? 'q-pl-xl' : ''"
      :style="$q.platform.is.desktop ? 'border-left: 1px solid grey;' : ''"
    >
      <div class="text-subtitle1 text-weight-bold">
        Registered Office Address:
      </div>
      <FooterItem
        v-for="(item, index) in items5"
        v-bind:key="index"
        v-bind:item="item"
      />
    </div>
  </div>
</template>

<script>
import FooterItem from "./FooterItem.vue";

const footerData1 = [
  {
    title: "About Us",
    link: "",
  },
  {
    title: "Careers",
    link: "",
  },
  {
    title: "Our Stories",
    link: "",
  },
  {
    title: "Press",
    link: "",
  },
];
const footerData2 = [
  {
    title: "Facebook",
    link: "",
  },
  {
    title: "Instagram",
    link: "",
  },
  {
    title: "Twitter",
    link: "",
  },
];
const footerData3 = [
  {
    title: "Return Policy",
    link: "",
  },
  {
    title: "Terms Of Use",
    link: "",
  },
  {
    title: "Security",
    link: "",
  },
  {
    title: "Privacy",
    link: "",
  },
  {
    title: "Sitemap",
    link: "",
  },
];
const footerData4 = [
  { title: "Payments", link: "" },
  { title: "Shipping", link: "" },
  { title: "Cancellation & Returns", link: "" },
  { title: "FAQ", link: "" },
];
const footerData5 = [
  {
    title: "335, Gokhale Wadi, Grant Road",
    link: "",
  },
  {
    title: "Mumbai, Maharashtra",
    link: "",
  },
  {
    title: "Cancellation & Returns",
    link: "",
  },
  { title: "412207", link: "" },
  { title: "India", link: "" },
];

import { useQuasar } from "quasar";

export default {
  name: "footer-index",
  components: {
    FooterItem,
  },

  data() {
    return {
      items1: footerData1,
      items2: footerData2,
      items3: footerData3,
      items4: footerData4,
      items5: footerData5,
      q: useQuasar(),
    };
  },
};
</script>
