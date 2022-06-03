<template>
  <h1>Vue18_select_binding</h1>
  <select name="sel" ref="m" id="sel"  v-model="selected" v-on:change="ch($event)">
      <option value="a">A</option>
      <option value="b">B</option>
      <option value="c">C</option>
      <option value="d">D</option>
      <option value="e">E</option>
  </select>
  <span>{{selected}},{{selText}}</span>
</template>

<script>
import { onMounted } from '@vue/runtime-core'
export default {
    data(){
        return{selected:"c",selText:""}
    },
    methods:
    {
        ch(e){
            this.selText = e.target.options[e.target.selectedIndex].text
},
    setup(){
        onMounted(()=>{
            const m = this.$refs.m;
            this.selText=m.options[m.selectedIndex].text
        })
    }
    }
}
</script>

<style>

</style>