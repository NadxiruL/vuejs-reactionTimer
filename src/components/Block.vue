<template>
  <div class="block" v-if="showBlock">click me</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
    };
  },
  //fire only when mounted to dom component.
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      console.log(this.delay);
    }, this.delay);
  },
  //fire when any data inside our dom is updated.
  updated() {
    console.log("test");
  },
  unmounted() {
    // todo here..
  },
};
</script>

<style>
.block {
  width: 300px;
  border-radius: 20px;
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px;
  margin: 40px auto;
}
</style>
