<template>
  <nut-button id="target" type="primary" @click="clickHandle">主要按钮</nut-button>
  <nut-tour
    v-model="showTour"
    :steps="step"
    type="tile"
    location="bottom-end"
  ></nut-tour>
</template>
<script setup lang="ts">
import { useDidShow } from '@tarojs/taro';
import { ref } from 'vue';
const showTour = ref(false);
const step = [{
  content: '70+ 高质量组件，覆盖移动端主流场景',
  target: 'target'
}];
useDidShow(() => {
  showTour.value = true;
})
const clickHandle = () => {
  console.log("点击了");
}
</script>

<style>
  .nut-tour-content-inner{
    white-space: nowrap
  }
</style>
