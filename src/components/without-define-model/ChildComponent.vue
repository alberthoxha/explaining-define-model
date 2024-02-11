<script setup lang="ts">
import {ref} from "vue";

const inputValue = ref('');

const emit = defineEmits<{
  (e: 'change', value: string): void
  (e: 'uppercase', value: boolean): void
}>()

const {msg} = defineProps<{
  msg: string,
}>()

const emitChange = () => {
  emit("change", inputValue.value);
}

const emitUppercase = () => {
  emit('uppercase', true);
}
</script>

<template>
  <div class="container">
    <h1>{{ msg }}</h1>
    <input type="text" placeholder="Write something" v-model="inputValue" @input="emitChange">
    <button @click="emitUppercase">To Uppercase</button>
  </div>
</template>

<style scoped>
.container{
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>