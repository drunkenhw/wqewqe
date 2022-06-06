<template>
    <h1>선언적 렌더링</h1>
  {{message}}
  <h3 v-text="message"></h3>
  <h3 v-html="message"></h3>
</template>

<script>
export default {
    data(){
        return {message : "<a href='https://naver.com'>vue3 programming</a>"}
    }
}
</script>

<style>

</style>