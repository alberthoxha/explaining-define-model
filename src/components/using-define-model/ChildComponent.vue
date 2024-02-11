<script setup lang="ts">
import {ref, watch} from "vue";

const inputValue = ref('');
const modelValue = defineModel<string | undefined>()

const changeToUppercase = () => {
  modelValue.value = modelValue.value?.toUpperCase()
}

watch(inputValue, (newValue) => {
  modelValue.value = newValue
})

</script>
<template>
  <div class="container">
    <h1>{{ modelValue }}</h1>
    <input type="text" placeholder="Write something" v-model="inputValue">
    <button @click="changeToUppercase">To Uppercase</button>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>