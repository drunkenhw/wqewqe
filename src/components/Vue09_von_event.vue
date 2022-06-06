<template>
  <h1>v-on key event</h1>
  <button @click="warn('warning', $event)">warning</button>
</template>

<script>
export default {
    methods:{
        warn(msg, e){
            if(e) e.preventDefault()
            alert(e)
            alert(msg)
        },
    }
}
</script>

<style>

</style>