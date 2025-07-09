<script setup>
import { RouterView } from 'vue-router'
import PighCounter from './components/pighCounter.vue'
import { ref } from 'vue';

const arr = ref([{
  name: 'Luna',age: 5, count: 2
},{
  name: 'Mbappe',age: 26, count: 9
}])

</script>

<template>
  <PighCounter v-for="pigh in arr" :name="pigh.name" :age="pigh.age" :count="pigh.count"/>

  <RouterView />
</template>

<style scoped></style>
