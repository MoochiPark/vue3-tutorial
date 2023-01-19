<template>
  <a href='#/declarative-rendering'>Declarative Rendering</a>
  <hr />
  <a href='#/attribute-bindings'>Attribute Bindings</a>
  <hr />
  <a href='#/event-listeners'>Event Listeners</a>
  <hr />
  <a href='#/form-bindings'>Form Bindings</a>
  <hr />
  <a href='#/conditional-rendering'>Conditional Rendering</a>
  <hr />
  <a href='#/list-rendering'>List Rendering</a>
  <hr />
  <a href='#/computed-property'>Computed Property</a>
  <hr class='separation-line' />
  <component :is='currentView' />
</template>

<script setup>
import AttributeBindings from "@/components/AttributeBindings.vue";
import EventListeners from "@/components/EventListeners.vue";
import FormBindings from "@/components/FormBindings.vue";
import ConditionalRendering from "@/components/ConditionalRendering.vue";
import ListRendering from "@/components/ListRendering.vue";
import DeclarativeRendering from "@/components/DeclarativeRendering.vue";
import ComputedProperty from "@/components/ComputedProperty.vue";

import { ref, computed } from "vue";

const routes = {
  "/declarative-rendering": DeclarativeRendering,
  "/attribute-bindings": AttributeBindings,
  "/event-listeners": EventListeners,
  "/form-bindings": FormBindings,
  "/conditional-rendering": ConditionalRendering,
  "/list-rendering": ListRendering,
  "/computed-property": ComputedProperty,
};

const currentPath = ref(window.location.hash);

window.addEventListener("hashchange", () => {
  currentPath.value = window.location.hash;
});

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || "/"];
});
</script>

<style scoped>
.separation-line {
  margin-bottom: 20px;
}
</style>