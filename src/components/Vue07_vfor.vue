<template>
  <h1>v-for</h1>

  <p v-for="k in num" :key="k">
    <span v-for="j in 9" :key="j"
      ><br />
      <span v-for="i in 3" :key="i"
        >&nbsp;&nbsp;
        <span v-if="i + k + 1 != 10">
          {{ i + 1 + k }}x{{ j }}={{ (i + 1 + k) * j }}
        </span>
        <span v-else> </span>
      </span>
    </span>
  </p>
</template>

<script>
export default {
  data() {
    return { num: [0, 3, 6] };
  },
};
</script>
<style></style>
