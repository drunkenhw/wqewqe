<template>
  <div id="apple">
      <p>{{title}}</p>
      <my-counter></my-counter>
   
  </div>
</template>

<script>
import { createApp, ref } from '@vue/runtime-dom'
const app =createApp({

})
    app.component('my-counter',{
        inject:['counter_header'],
        setup(){
            const count = ref(0)
            return {count}
        },
    template:`
    <span>{{counter_head}}</span>
    <button @click="count++" v-text="count"></button>
    <hr>`
    }),
    app.config.globalProperties.title ='Vue 3 Demo'
    app.provide('counter_head','my-counter')
    app.mount('#apple')
export default {
}
</script>

<style>

</style>