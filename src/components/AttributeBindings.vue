<template>
  <h1 :class='titleClass'>나를 빨갛게 만들어 보세요</h1>
</template>

<script setup>
import { ref } from "vue";

const titleClass = ref("title");
</script>

<style scoped>
.title {
  color: red;
}
</style>