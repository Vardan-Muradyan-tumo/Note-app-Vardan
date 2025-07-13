ճSZ<template>
    <div class="Add-popup">
        <div class="note-form">
            <div class="cls-btn">
                <close_button @click="$emit('onClose')" />
            </div>
            <h1 class="title"> title</h1>
            <input class="vernagur" v-model="title" />
            <textarea class="lorem" v-model="content"></textarea>
            <button class="save" @click="$emit('onSave', title, content)">SAVE</button>
        </div>
    </div>
</template>
<script setup>
import { ref } from 'vue';
import close_button from './close_button.vue'
const title = ref('')
const content = ref('')
</script>
<style scoped>
.Add-popup {
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgba(0, 0, 0, 0.4);
    display: flex;
    justify-content: center;
    align-items: center;
}

.note-form {
    width: 580px;
    padding: 30px 32px 40px;
    background: linear-gradient(114.43deg, rgba(255, 255, 255, 0.6) 4%, rgba(255, 255, 255, 0.1) 100%);
    display: flex;
    flex-direction: column;
    gap: 10px;
    border-radius: 10px;
    position: relative;
}

.title {

    font-weight: 500;
    font-style: Medium;
    font-size: 24px;
    margin: 0;
    line-height: 100%;
    letter-spacing: 0%;
    padding: 0;
    text-align: left;

}

.note-form input {
    width: 100%;
    height: 40px;
    border-radius: 4px;

}

.note-form textarea {
    width: 100%;
    resize: none;
    height: 80px;
    border-radius: 4px;
}

.note-form .save {
    width: 100%;
    height: 40px;
    border-radius: 4px;
    color: white;
    font-size: 20px;
    font-weight: 500;
    border: none;
    background: linear-gradient(90deg, #B4FBF3 0%, #23926F 100%);
    cursor: pointer;
}

.note-form .save:hover {
    background: linear-gradient(90deg, #265b55 0%, #0ed797 100%);
}

.cls-btn {
    position: absolute;
    top: 8px;
    right: 8px;
}
</style>