<template>
  <h1>v-on capture, self</h1>
  <div v-on:click="doTop" id="top">
    <div v-on:click.self="doMiddle" id="middle">
      <button type="button" v-on:click="doBottom">Bubble</button>
    </div>
  </div>
  stop은 자신만 이벤트를 실행할 경우<br>
  capture는 자신보다 parent의 이벤트를 먼저 실행,이럴 경우 parent에 capture를 붙임.<br>
  상위 노드에 capture가 연속적일 경우 마지막으로 적용된 노드가 먼저 시작.<br>
  self는 자신이 직접 발생한 이벤트만 처리.<br>
</template>

<script>
export default {
  methods:{
    doTop()    {console.log('Top    이벤트 발생.');},
    doMiddle() {console.log('Middle 이벤트 발생.');},
    doBottom() {console.log('Bottom 이벤트 발생.');},
  }
};
</script>

<style>
  #top    {width: 200px;height: 200px; background: pink;}
  #middle {width: 100px;height: 100px; background: greenyellow;}
</style>