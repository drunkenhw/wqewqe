<template>
  <h1>Vue17_radio_binding</h1>
  <label for="a">A</label>
  <input type="radio" name="A" id="a" v-model="se" v-bind:value="'A'">
  <label for="b">B</label>
  <input type="radio" name="A" id="b" v-model="se"  v-bind:value="'B'">
  <label for="c">C</label>
  <input type="radio" name="A" id="c" v-model="se"  v-bind:value="'C'">
  <br>
  <span>{{se}}</span>
  <input type="hidden" name="choice" v-text="se">
</template>

<script>
export default {
    data(){
        return{se:"A"}
    }
}
</script>

<style>

</style>