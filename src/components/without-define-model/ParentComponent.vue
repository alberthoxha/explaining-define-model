<script setup lang="ts">
import { ref } from "vue";
import ChildComponent from "./ChildComponent.vue";

const parentMessage = ref("hello, from the parent!");

const handleChildChange = (updatedMessage: string) => {
  parentMessage.value = updatedMessage;
}

const handleUppercaseChange = (shouldUppercase: boolean) => {
  if (shouldUppercase) {
    parentMessage.value = parentMessage.value.toUpperCase();
  }
}
</script>

<template>
  <ChildComponent
      :msg="parentMessage"
      @change="handleChildChange"
      @uppercase="handleUppercaseChange"
  />
</template>
