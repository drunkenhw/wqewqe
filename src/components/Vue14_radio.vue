<template>
  <label for="one">one</label>
  <input type="radio" name="radio" id="one" value="one" v-model="picked"><br>
  <label for="two">two</label>
  <input type="radio" name="radio" id="two" value="two" v-model="picked"><br>
  <span>picked : {{picked}}</span>
</template>

<script>
export default {
    data(){
        return { picked:""}
    }
}
</script>

<style>

</style>