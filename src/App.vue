<script setup>
import { ref, reactive, onMounted, onUpdated, onUnmounted } from 'vue';
const data = reactive({
  颜色1: '绿色',
  颜色2: '黄色',
  颜色3: '蓝色',
});
const change = () => {
  data['颜色1'] = '白色';
};
const msg = ref('Hello World!');
const obj = reactive({
  name: 'wy',
});
const add = ({ value = '123', name = 'ss' }) => {
  msg.value = value;
  obj.name = name;
};
onMounted(() => {
  console.log('mounted!');
});
onUpdated(() => {
  console.log('updated!');
});
onUnmounted(() => {
  console.log('unmounted!');
});
</script>

<template>
  <div>
    <p class="绿色">{{ data.颜色1 }}</p>
    <p class="黄色">{{ data.颜色2 }}</p>
    <p class="蓝色">{{ data.颜色3 }}</p>
    <button @click="change">改</button>
  </div>
</template>

<style scoped>
.绿色 {
  color: green;
}
.黄色 {
  color: yellow;
}
.蓝色 {
  color: blue;
}
</style>
