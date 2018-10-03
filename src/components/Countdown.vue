<template lang="pug">
  div
    h1 countdown
    p {{ seconds }}
</template>

<script>
export default {
  data() {
    return {
      seconds: 20
    };
  },
  created() {
    setInterval(this.tick, 1000);
  },
  destroyed() {
    clearInterval(this.tick);
  },
  methods: {
    tick() {
      if (this.seconds <= 0) {
        // console.log(`this.seconds <= 0!!!`);
        // clearInterval(this.tick);
        return;
      }
      this.seconds = this.seconds - 1;
    }
  }
};
</script>

<style scoped>
div {
  position: fixed;
  right: 0;
  bottom: 0;
  padding: 1rem;
  text-align: right;
}
p {
  margin: 0;
}
</style>
