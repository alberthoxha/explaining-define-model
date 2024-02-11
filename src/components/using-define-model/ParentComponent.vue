<script setup lang="ts">
import {ref} from "vue";
import ChildComponent from "./ChildComponent.vue";

const parentMessage = ref("hello, from the parent!");
</script>

<template>
  <ChildComponent
      v-model="parentMessage"
  />
</template>
