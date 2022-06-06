<template>
<h1>checkbox</h1>
    <label for='single'>sdasdasda</label>
  <input type="checkbox" name="" id="single" v-model="a" v-bind:true-value="'체크됨'" v-bind:false-value="'체크되지않음'">
  <span>{{a}}</span>
</template>

<script>
export default {
    data(){
        return{a:'a'}
    }
}
</script>

<style>

</style>