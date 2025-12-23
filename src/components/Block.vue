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
  mounted() {
    console.log(`Block mounted`);
    setTimeout(() => {
      this.showBlock = true;
      console.log("Block is now visible after delay of " + this.delay + "ms");
    }, this.delay);
  },
  updated() {
    console.log("Block updated");
  },
  unmounted() {
    console.log("Block unmounted");
  },
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 20px;
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>