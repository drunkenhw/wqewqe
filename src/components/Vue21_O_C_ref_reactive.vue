<!--<template>
  <h1>Options API Data</h1>
  <button @click="count++">count is {{count}}</button>
</template>

<script>
    
export default {
    data(){
        return {count:1};
    }

}
</script>
-->

<!-- <template>
  <h1> Options API Methods</h1>
  <button @click="addOne">Add</button>
  <span ref="result"> count is {{count}}</span>
</template>

<script>
    
export default {
    data(){
        return {count:1};
    },
    methods:{
        addOne : function(){
            this.count++
            this.$refs.result.textContent = `count ${this.count}`
        }
    }

}
</script>

<style>

</style> -->
<!-- 
<template>
  <h1> Composition API ref</h1>
  <button @click="addOne">Add</button>
  <span ref="result"> count is </span>
</template>

<script>
import { ref } from '@vue/reactivity'
    
export default {
   setup(){
       const count = ref(0)
       const result = ref('')
       function addOne(){
           
           result.value.textContent=` count is ${++count.value}`
       }

       return{addOne,count, result}
   }

}
</script>

<style>

</style> -->

<template>
  <h1> Composition API reactive</h1>
  <button @click="addOne">Add</button>
  <span ref="result"> count is </span>
</template>

<script>
import { reactive, ref } from '@vue/reactivity'
    
export default {
   setup(){
       const state = reactive({
           count:ref(10)
       })
       const result = ref('')
       function addOne(){
           
           result.value.textContent=` count is ${++state.count}`
       }

       return{addOne,state, result}
   }

}
</script>

<style>

</style>