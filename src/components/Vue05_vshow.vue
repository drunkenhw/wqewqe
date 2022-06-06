<template>
  <h1>v-show</h1>
  <span v-show="flag" v-text="msg"></span>
</template>

<script>
const vm = {
  data: () => {
    return { msg: "notice", flag: 1 };
  },

  methods: {
    toggle() {
      this.flag ^= 1;
    },
  },
  mounted() {
    setInterval(() => {
      this.toggle();
    }, 1000);
  },
};
export default vm;
</script>

<style></style>
