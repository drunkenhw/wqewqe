<template>
  <div v-bind:id="dynamicId">Hello</div>
  <img v-bind:src="url + '200x100'" />
  <div v-bind:class="[classA, classB]"></div>
  <div v-bind:style="[styleA, styleB]"></div>
  <div v-bind="{id:box, 'data-url':url}"></div>
</template>

<script>
export default {
  data() {
    return {
      dynamicId: "first_div",
      url: "https://via.placeholder.com/",
      classA: "rect",
      classB: "fill",
      styleA: "background:green;border-radius:50px",
      styleB: " width:100px;height:100px;border: 1px solid black",
    };
  },
};
</script>

<style>
.rect {
  width: 100px;
  height: 100px;
  border: 1px solid red;
}
.fill {
  background: blue;
}
</style>
