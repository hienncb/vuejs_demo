<template>
  <div class="flex justify-center" style="margin-top: 20px">
    <q-img
      src="https://scontent.fsgn4-1.fna.fbcdn.net/v/t39.30808-6/273378063_2734418026852182_5739766385016576235_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=174925&_nc_ohc=3MFrhuuFxOAAX84IrnK&_nc_ht=scontent.fsgn4-1.fna&oh=00_AfBwQIbzmeau_Sw7hY4XCTSlqpsG_ol3ojLRbO8svXTKYA&oe=644B8498"
      spinner-color="white"
      img-class="my-custom-image"
      class="img-avata"
    />
  </div>
  <div class="flex justify-center textHead">{{ accountName }}</div>
</template>

<script>
export default {
  name: "compo-draw-account",
  setup() {
    return {
      accountName: "Hienncb",
    };
  },
};
</script>
<style>
.img-avata {
  border-radius: 50%;
  -moz-border-radius: 50%;
  -webkit-border-radius: 50%;
  width: 60px;
  height: 60px;
}

.textHead {
  margin-top: 10px;
  font-weight: bold;
}
</style>
