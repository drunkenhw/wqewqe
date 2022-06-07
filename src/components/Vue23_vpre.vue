<template>
  <h1>v-pre</h1>
  <div>{{ greet(msg) }}</div>
  <div v-pre>
    {{ msg }}
    <div>{{ greet(msg) }}</div>
  </div>
</template>

<script>
export default {
  setup() {
    const msg = "Vue3";
    function greet(msg){
        return 'hello' + msg
    }
    
        return { msg, greet };
  },
};
</script>

<style></style>
