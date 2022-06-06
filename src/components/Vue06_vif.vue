<template>
  <h1>v-if</h1>
  <div v-if="x > 23">e{{ x }}</div>
  <div v-else>g{{ x }}</div>
  <div v-if="score>=90">A</div>
  <div v-else-if="score>=80">B</div>
  <div v-else-if="score>=70">C</div>
  <div v-else>F</div>
</template>

<script>
const num = 30
export default {
  data() {
    return { x: Math.floor(Math.random() * 45) + 1 ,
    score:num};
  },
};
</script>

<style></style>
