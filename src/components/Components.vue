<template>
  <ChildComp :msg='greeting' @response='(msg) => childMsg = msg'>
    부모로부터: {{ msg }}
  </ChildComp>
  <h2>부모 컴포넌트</h2>
  <p>{{ childMsg }}</p>

</template>

<script setup>
import { ref } from "vue";
import ChildComp from "@/components/ChildComp.vue";

const greeting = ref("부모 컴포넌트로부터 💌을 전달받았어요!");

const childMsg = ref("자식 컴포넌트로부터 아직 메시지를 받지 못했어요!");

const msg = ref("Vue는 개발자에게 정말 유용하죠! 🎁");
</script>
