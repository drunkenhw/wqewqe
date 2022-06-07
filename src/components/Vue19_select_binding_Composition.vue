<template>
  <h1>form element select binding Composition API</h1>
  select는 바인딩을 할 때 option의 value에 binding을 한다.
  <select
    name="selItem"
    ref="selItem"
    id="selItem"
    v-model="selected"
    v-on:change="selChange"
  >
    <option value="반지">ring</option>
    <option value="목걸이">necklace</option>
    <option value="귀걸이">earring</option>
    <option value="시계">watch</option>
    <option value="팔찌">bracelet</option>
  </select>
  <span>{{ selected }} / {{selectText}}</span><br>
  <span>{{ selected }} / <span ref="selText" id="selText"></span></span>
</template>

<script>
import { ref,onMounted } from '@vue/runtime-core';
export default {
  
  setup() {
    const selItem = ref(null)
    const selText = ref(null)
    const selected = '시계'
    const selectText = ref('')
    const getSelText= (function() {
       selChange()
    })
    const selChange = function(){
        const tmp = selItem.value.options[selItem.value.selectedIndex].text;
      selectText.value = tmp
      selText.value.textContent = tmp
    }
    onMounted(() =>{
      getSelText()
    })
    return {
       selectText,selItem,selText,selected,getSelText,selChange
    }

  },
};
</script>

<style></style>
