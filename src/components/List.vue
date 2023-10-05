<script setup lang="ts">
import {watch} from "vue"
type listType = {
  id: number
  text: string
}[]

  let id = 0
  const mockList:listType= [
    {id: id++, text: "テスト1"},
    {id: id++, text: "テスト2"},
    {id: id++, text: "テスト3"}
  ]

  type Props = {
    text: string
  }
  const props = defineProps<Props>()

  watch(props, () => {
    console.log(props.text)
    mockList.push({id: mockList.length + 1, text: props.text})
    console.log(mockList)
});



</script>

<template>
  <ul>
    <li v-for="item in mockList" :key="item.id">{{ item.text }}</li>
  </ul>
</template>

<style scoped>
</style>