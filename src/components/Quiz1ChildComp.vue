<template>
  <div class='child'>
    <h2>자식 컴포넌트</h2>
    <div>
      부모로부터 받은 메시지:
      <slot>대체: 부모로부터 컨텐츠를 못 받았어요! 🥲</slot>
    </div>
    <input v-model='msg' placeholder='자식 입력'>
    <button @click='confirm'>전달</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const emit = defineEmits(["confirm"]);

const msg = ref("");

function confirm() {
  emit("confirm", msg.value);
}
</script>

<style scoped>
.child {
  background-color: aquamarine;
}
</style>