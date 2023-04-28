<template>
  <div
    @click="$router.push('/details')"
    class="col-lg-2 col-md-2 col-sm-12 col-xs-12 text-center full-height section-item"
  >
    <div>
      <q-img
        style="height: 170px; max-width: 300px"
        src="https://scontent.fhan4-3.fna.fbcdn.net/v/t1.15752-9/342550231_561956512701800_6361906036911888711_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=ae9488&_nc_ohc=scK_8EA5tYsAX-6-akY&_nc_ht=scontent.fhan4-3.fna&oh=03_AdQai6OQygJpFx4vwcXuTHwpudUxe9PdlWIalaGKBoFdVg&oe=646F098C"
        class="rounded-borders col-lg-3 col-md-3 col-sm-12 col-xs-12 cursor-pointer full-height"
        alt="failt"
      />
    </div>
    <div style="text-align: center">
      <div class="name-type">name</div>
      <div class="price-type">1000d</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    price: String,
  },
};
</script>

<style>
.name-type {
  font-family: Lato;
  font-weight: 700;
  color: black;
  font-size: 14px;
}
.price-type {
  font-family: Lato;
  color: #4caf50 !important;
  font-weight: bold;
  font-size: 0.75rem;
}
</style>
