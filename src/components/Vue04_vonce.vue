<template>
  <h1>v-once</h1>
  <span v-once >{{msg1}}</span><br>
  <span v-text="msg1"></span><br>
  <button v-on:click="a">ss</button><br>
  <input type="text" v-model="msg1">
</template>

<script>
var data = {msg1 : "v-once임"}
export default {
    data(){
        return data
    },
   methods:{
       a: function() {
            this.msg1 = "v-onve아님";
            return this.msg1;
       }
   }

}

</script>

<style>

</style>