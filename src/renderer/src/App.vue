<script setup lang="ts">
import Versions from './components/Versions.vue';
import Test from './components/Test.vue';
import { onMounted, ref } from 'vue';
const ipcHandle = () => window.electron.ipcRenderer.send('ping');
const flag = ref(true);
onMounted(() => {
  setTimeout(() => {
    flag.value = false;
  }, 10000);
});
</script>

<template>
  <Test v-if="flag" />
  <Versions />
</template>
