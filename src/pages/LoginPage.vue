<template>
  <q-layout>
    <q-page-container>
      <q-page class="flex flex-center" style="font-family: Lato">
        <q-card
          :style="$q.platform.is.desktop ? 'width:55%;' : ''"
          class="row my-card items-center q-pa-none q-ma-none shadow-24"
        >
          <q-card-section
            v-if="$q.platform.is.desktop"
            class="col-md-4 col-lg-4 col-sm-12 sol-xs-12 items-center float-left"
            style="background-color: #1f509e"
            :style="{ height: win_height - 270 + 'px' }"
            horizontal
          >
            <div class="text-center full-width">
              <div><img src="images/logo.png" style="width: 33%" /></div>
              <div class="text-weight-bolder text-white text-h6">
                Quasar Shopping
              </div>
              <div class="text-caption text-white">
                Quasar Shopping - One stop solution
              </div>
            </div>
          </q-card-section>
          <q-card-section
            class="col-md-8 col-lg-8 col-sm-12 sol-xs-12 float-left"
          >
            <q-card-section class="items-center">
              <div>
                <div
                  v-if="!$q.platform.is.desktop"
                  class="text-weight-bolder text-center q-mb-md text-primary text-h6"
                >
                  Quasar Shopping
                </div>
                <q-form
                  :style="
                    $q.platform.is.desktop
                      ? 'width:55%;margin: auto;'
                      : 'margin: auto;'
                  "
                  class="q-gutter-md"
                >
                  <span class="text-subtitle1 text-weight-bold text-grey-7"
                    >Welcome Aboard</span
                  >
                  <q-input
                    dense
                    outlined
                    v-model="username"
                    label="Username"
                    lazy-rules
                  />

                  <q-input
                    dense
                    type="password"
                    outlined
                    v-model="password"
                    label="Password"
                    lazy-rules
                  />
                  <q-checkbox
                    class="text-grey-8"
                    dense
                    v-model="remember_me"
                    label="Remember me"
                  />
                  <div>
                    <q-btn
                      class="text-capitalize"
                      size="sm"
                      style="width: 75px"
                      dense
                      label="Login"
                      type="button"
                      color="primary"
                      :loading="progress[0].loading"
                      :percentage="progress[0].percentage"
                      v-on:click="login"
                    >
                      <template v-slot:loading>
                        <q-spinner-gears class="on-left" />
                        Computing...
                      </template>
                    </q-btn>
                    <!-- </div> -->
                    <q-btn
                      class="float-right text-blue-9 text-capitalize"
                      size="sm"
                      style="width: 75px; border: 1px solid #36669e"
                      dense
                      label="Sign Up"
                      type="button"
                    />
                  </div>
                </q-form>
              </div>
            </q-card-section>
          </q-card-section>
        </q-card>
      </q-page>
    </q-page-container>
  </q-layout>
</template>
<script>
import { useQuasar } from "quasar";
import axios from "axios";

import { ref, onBeforeUnmount } from "vue";
export default {
  data() {
    const progress = ref([
      { loading: false, percentage: 0 },
      { loading: false, percentage: 0 },
      { loading: false, percentage: 0 },
    ]);

    const intervals = [null, null, null];

    function startComputing(id) {
      progress.value[id].loading = true;
      progress.value[id].percentage = 0;

      intervals[id] = setInterval(() => {
        progress.value[id].percentage += Math.floor(Math.random() * 8 + 10);
        if (progress.value[id].percentage >= 100) {
          clearInterval(intervals[id]);
          progress.value[id].loading = false;
        }
      }, 700);
    }

    onBeforeUnmount(() => {
      intervals.forEach((val) => {
        clearInterval(val);
      });
      this.login();
    });

    return {
      username: "hienncb",
      password: "123456",
      remember_me: false,
      q: useQuasar(),
      info: "asdsad",
      progress,
      startComputing,
    };
  },
  methods: {
    login() {
      this.startComputing(0);
      axios
        .get("https://api.coindesk.com/v1/bpi/currentprice.json")
        .then(
          (response) => (this.info = response.data.chartName),
          this.$router.push("/home")
          // log
        )

        .catch((error) => console.log(error));
    },
  },

  computed: {
    win_width() {
      return this.$q.screen.width - 59;
    },
    win_height() {
      return this.$q.screen.height - 0;
    },
  },
};
</script>

<style>
.my-card {
  /*width: 55%;*/
  height: 30%;
}

#particles-js {
  position: absolute;
  width: 100%;
  height: 100%;
  /*background: linear-gradient(145deg, #abbaab 15%, #ffffff 70%);*/
  /*background: linear-gradient(145deg,#f7f8f8 11%, #627e79 75%);*/
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 50% 50%;
}

.login-form {
  position: absolute;
}
</style>
