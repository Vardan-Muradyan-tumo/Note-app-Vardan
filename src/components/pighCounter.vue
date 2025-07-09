<template>
<div class="card">
    <h1>{{ props.name }}</h1>
    <h2>{{ props.age }}</h2>
<h1>{{ counter }}</h1>
<button @click="pighShatacnel">click me</button>   
</div>

</template>
<script setup>
import{ref, defineProps} from 'vue'
const props = defineProps(['name', 'age'])



let counter = ref(props.age)
function pighShatacnel(){
    counter.value++
}
</script>
<style scoped>
.card{
    width: 300px;
    height: 300px;
    border: 1px solid gray;
    border-radius: 6px;
    display: flex;
    align-items:center ;
    justify-content: center;
    flex-direction: column;
}
</style>