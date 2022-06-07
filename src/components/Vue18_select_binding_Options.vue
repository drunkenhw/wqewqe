<template>
  <h1>form element select binding Options API</h1>
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
  <span>{{ selected }} / <span ref="selectText" id="selText"></span></span>
</template>

<script>
// import { onMounted } from '@vue/runtime-core';
export default {
  // Options API 방식 :: Vue2.X
  data: () => ({ selected: "반지", selectText: "" }),
  methods: {
    selChange() {
      // const sel = e.target;
      // const selectText = this.$refs.selectText;
      // this.selectText = sel.options[sel.selectedIndex].text;
      // selectText.textContent = sel.options[sel.selectedIndex].text;
      this.getSelText()
    },
    getSelText() {
      // $refs 접근
      const selectText = this.$refs.selectText;
      const selItem = this.$refs.selItem;
      this.selectText = selItem.options[selItem.selectedIndex].text
      selectText.textContent = selItem.options[selItem.selectedIndex].text;
      console.log(this.selectText);
      // DOM 접근
      // const selItem = document.querySelector('#selItem')
      // const selText = document.querySelector('#selText')
      // this.selectText = selItem.options[selItem.selectedIndex].text
      // selText.textContent = selItem.options[selItem.selectedIndex].text
    },
  },
  mounted: function () {
    this.getSelText();
  },

};
</script>

<style></style>
