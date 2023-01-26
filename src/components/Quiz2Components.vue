<template>
  <div class='parent'>
    <h2>부모 컴포넌트</h2>
    <h3 v-if='toggle'>True</h3>
    <h3 v-else>False</h3>
    <Quiz2ChildComp @toggle='toggle = !toggle' />
  </div>
</template>

<script setup>
import { ref } from "vue";
import Quiz2ChildComp from "@/components/Quiz2ChildComp.vue";

const toggle = ref(false);
</script>

<style scoped>
.parent {
  background-color: greenyellow;
}
</style>