<template>
    <div class="card">
        <div class="cls-btn">
            <close_button @click="$emit('onDelete')" />
        </div>
        <p class="title">{{ props.title }}</p>
        <p class="component">{{ props.content }}
        </p>
        <p class="time">{{ props.time }}</p>
    </div>
</template>
<script setup>
import close_button from './close_button.vue'
const props = defineProps(['title', 'content', 'time'])
import { defineProps } from 'vue'
</script>
<style scoped>
.card {
    width: 300px;
    height: 210px;
    border: 1px solid white;
    border-radius: 14px;
    background: linear-gradient(114.43deg, rgba(255, 255, 255, 0.6) 4%, rgba(255, 255, 255, 0.1) 100%);
    padding: 18px 20px 8px 20px;
    position: relative;

}

.title {

    font-weight: 600;
    margin-bottom: 20px;
    font-size: 28px;

    line-height: 100%;
    letter-spacing: 0%;
}

.component {
    font-weight: 400;
    font-style: Regular;
    font-size: 18px;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 3;
    padding-bottom: 2px;
    width: 100%;
    overflow: hidden;
    min-height: ևթpx;
    line-height: 100%;
    letter-spacing: 0%;

}

.time {

    font-weight: 500;
    font-style: Medium;
    font-size: 15px;

    line-height: 100%;
    letter-spacing: 0%;
    text-align: right;
    margin-top: 50px;
    color: #797979;

}

.cls-btn {
    position: absolute;
    top: 8px;
    right: 8px;
    opacity: 0;
    transition: 0.3s;
}

.card:hover .cls-btn {
    opacity: 1;
}
</style>