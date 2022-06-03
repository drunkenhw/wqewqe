<template>
  <h1>select</h1>
  <select v-model="selected">
      <option value="" disabled>select</option>
      <option >A</option>
      <option >b</option>
      <option >c</option>
  </select>
  <span>{{selected}}</span>
  <select v-model="arrSelect" multiple>
      <option value = "" disabled> sele</option>
      <option v-for="item in arr" :key="item"  v-bind:value="item.value">{{item.text}}</option>
  </select>
  <span>{{arrSelect}}</span>
</template>

<script>
export default {
    data(){
        return{selected:"",
        arrSelect:"",
        arr: [
            {text:'one',value:'a'},
            {text:'two',value:'b'},
            {text:'three',value:'c'},
            {text:'four',value:'d'},
        ],
        arrStr:["A",'B','C','D']
        }
    }

}
</script>

<style>

</style>