<script setup lang="ts">
  import {ref} from "vue"
  import Input from "@/components/Input.vue"
  import List from "@/components/List.vue"

  const text = ref("")
  const childText = (e: string) => {
    console.log("inputの値", e)
    console.log("textの値", text.value)
    text.value = e
  }


</script>

<template>
  <div class="wrap">
    <div class="title">TODOリストの作成</div>
    <Input @emit-submit="childText" />
    <List v-bind:text="text"/>
    <div>子からの値を受け取った：{{ text }}</div>
  </div>
</template>

<style scoped>
  .wrap {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-top: 20px;
  }

.title {
  font-size: 20px;
  font-weight: bold;
}
</style>
