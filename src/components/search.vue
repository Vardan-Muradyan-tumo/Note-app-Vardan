<template>
    <div><input v-model="search" placeholder="🔍Search note..." class="search" type="Search">
        <button class="b" @click="$emit('onSearch', search)">Search</button>
    </div>

</template>
<script setup>
import{ref} from 'vue';

const search = ref('')

</script>
<style scoped>
.search {
    display: flex;
    width: 150px;
    height: 20px;
    background-color: rgba(42, 177, 9, 0.4);
    gap: 6px;
}

.b {
      display: flex;
    width: 55px;
    height: 20px;
  background-color:  rgba(10, 140, 5, 0.4);
}
</style>