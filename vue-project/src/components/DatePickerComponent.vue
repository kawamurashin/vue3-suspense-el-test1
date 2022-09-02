<script lang="ts" setup>
import { ref } from 'vue'
const select = ref('')
let list:Date[] = []
const disabledDate = (time: Date) => {
  let result = list.find(v => v.getTime() == time.getTime())
  if(result){
    return true;
  }
  return false
}
const sleep = async () => {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve(1)
    }, 3000)
  })
}
await sleep();
const date = new Date();
let tomorrow = new Date(date.getFullYear(),date.getMonth(),date.getDate(),0,0,0,0);
tomorrow.setDate(tomorrow.getDate() + 1)
list.push(tomorrow)
</script>

<template>
  <el-date-picker
      v-model="select"
      type="date"
      placeholder="Pick a day"
      :disabled-date="disabledDate"
  />
</template>
