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
                <div class="q-title">
                    <h2>{{ item.title }}</h2>
                <p v-if="selectedFag === item.id">{{ item.paragraph }}</p>
                </div>
                <div class="btn">
                    <button @click="toggleFag(item.id)" :class="{ active: selectedFag === item.id }"></button>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Work+Sans:ital,wght@0,100..900;1,100..900&display=swap');
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
    font-family: "Work Sans", sans-serif;
}
.title {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
    gap: 10px;
}
.title img {
    width: 40px;
    height: 40px;
}
.data {
    margin-top: 20px;
}
.question {
    margin-bottom: 20px;
    border-bottom: 1px solid #E0E0E0;
    display: flex;
    justify-content: space-between;
    padding-bottom: 15px;
}
.qtitle {
    justify-content: start;
}
.btn {
    flex: 0;
    display: flex;
    align-items: center;
    justify-content: center;
}
h1{
    font-weight: 700;
    font-size: 56px;
    color: #301534;
}
h2{
    font-size: 18px;
    font-weight: 600;
    padding-bottom: 10px;
}
p{
    font-size: 16px;
    color: hsl(292, 16%, 49%);
    line-height: 1.5;
}

button  {
    background-color: transparent;
    border: none;
    cursor: pointer;
    width: 30px;
    height: 30px;
    background-image: url('../assets/images/icon-plus.svg');
    background-size: cover;
    justify-items: flex-end;
}
button.active {
    background-image: url('../assets/images/icon-minus.svg');
}
</style>
