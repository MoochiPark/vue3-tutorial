<template>
  <h1>{{ message.split("").reverse().join("") }}</h1>
  <p>숫자 세기: {{ counter.count }}</p>
  <button @click='counter.count++'>증가</button>
  <h1>{{ value }}</h1>
  <button @click='value += "a"'>증가</button>
</template>

<script setup>
import { reactive, ref } from "vue";

let value = "hello";
const counter = reactive({
  count: 0,
});
const message = ref("안녕 Vue!");
message.value = "안녕하세요";
</script>

<style lang='scss' scoped>

</style>