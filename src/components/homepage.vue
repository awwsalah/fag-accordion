<script setup>
import { ref } from 'vue'
import data from '@/data.json'

const fagData = ref(data)
const selectedFag = ref(null)
const toggleFag = (id) => {
    selectedFag.value = selectedFag.value === id ? null : id
}

</script>


<template>
    <div class="container">
        <div class="title">
            <img src="../assets/images/icon-star.svg" alt="">
            <h1>FAQs</h1>
        </div>
        <div class="data">
            <div class="question" v-for="item in fagData" :key="item.id">
                <h2>{{ item.title }}</h2>
                <p v-if="selectedFag === item.id">{{ item.paragraph }}</p>
                <button @click="toggleFag(item.id)"><img src="../assets/images/icon-plus.svg" alt=""></button>
            </div>
        </div>
    </div>
</template>


<style scoped>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.container {
    max-width: 600px;
    background-color: #fff;
    border-radius: 10px;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
.title {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
    gap: 10px;
}
.data {
    margin-top: 20px;
}
</style>