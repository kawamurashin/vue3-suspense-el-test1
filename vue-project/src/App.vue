<template>
  <Suspense>
    <template #default>
      <DatePickerComponent></DatePickerComponent>
    </template>
    <template #fallback>
      <span>読み込み中…</span>
    </template>
  </Suspense>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import DatePickerComponent from './components/DatePickerComponent.vue';
export default defineComponent({
  name: 'App',
  components: {
    DatePickerComponent
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
