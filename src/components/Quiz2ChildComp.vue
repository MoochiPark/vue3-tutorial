<template>
  <div class='child'>
    <h2>자식 컴포넌트</h2>
    <button @click='emit("toggle")'>토글 버튼</button>
  </div>
</template>

<script setup>
const emit = defineEmits(["toggle"]);
</script>

<style scoped>
.child {
  background-color: aquamarine;
}
</style>