<template>
  <h2>자식 컴포넌트</h2>
  <h2>{{ msg || "prop이 아직 전달되지 않았습니다!" }}</h2>
  <slot>대체: 부모로부터 컨텐츠를 못 받았어요! 🥲</slot>
</template>

<script setup>
const props = defineProps({
  msg: String,
});

const emit = defineEmits(["response"]);

emit("response", "자식 컴포넌트로부터 🌷를 받았어요!");
</script>