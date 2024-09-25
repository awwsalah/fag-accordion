<script setup>
import homepage from './components/homepage.vue';
</script>

<template>
  <div>
    <homepage />
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
    background-color: #F8EEFF;
    width: 100%;
    height: 100dvh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-image: url('../assets/images/bg-pattern-desktop.svg');
    background-size: cover;
    background-repeat: no-repeat;
}
</style>