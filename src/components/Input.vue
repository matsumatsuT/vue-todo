<script setup lang="ts">
  import { ref } from 'vue'

  const message = ref("")
  const emit = defineEmits(['emit-submit'])

  // ボタン押下時のイベント
  const onSubmit = () => {
    console.log(message.value)
    emit("emit-submit", message.value)
    message.value = ""
  }
</script>

<template>
  <div class="input-wrap">
    <input type="text" v-model="message">
    <button type="button" @click="onSubmit">クリック</button>
  </div>
</template>

<style scoped>
  .input-wrap {
    display: flex;
  }

  input {
    margin-right: 10px;
  }
</style>