<template>
  <div class='parent'>
    <h2>부모 컴포넌트</h2>
    <input v-model='msg' placeholder='부모 입력'>
    <button @click='confirm'>전달</button>
    <div>
      자식으로부터 받은 메시지: {{ fromChildMsg }}
    </div>
    <TestChildComp @confirm='childConfirm'>{{ childMsg }}</TestChildComp>
  </div>
</template>

<script setup>
import { ref } from "vue";
import TestChildComp from "@/components/Quiz1ChildComp.vue";

const msg = ref("");
const childMsg = ref("");
const fromChildMsg = ref("");

function confirm() {
  childMsg.value = msg.value;
}

function childConfirm(value) {
  fromChildMsg.value = value;
}
</script>

<style scoped>
.parent {
  background-color: greenyellow;
}
</style>