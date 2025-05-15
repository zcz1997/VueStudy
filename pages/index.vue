<template>
  <div style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;padding: 2px;">
    <h1 style="color: green">✅ My Nuxt App is working！</h1>
    <p >This is a simple Nuxt.js app with a few basic pages and components.</p>
    <p style=" font-size: 18px; font-family: 'Times New Roman', Times, serif;">Welcome to my Nuxt App!</p>    
    <img src="https://avatars.githubusercontent.com/u/33356927?v=4" alt="logo" style="width: 100px; height: 100px;" />
    <a href="https://github.com/zcz1997" style="color: aqua;" target="_blank">click to go to my github</a>
    <p style="text-align: center;">Today is first day i learn Vue.js</p>
    <button style="color: azure;border-radius: 20px; background-color: black; padding: 10px 20px; cursor: pointer;" @click="increment">click me</button>
    <p>you clicked me {{ count }} times</p>
    <p>ようこそ、以下是每日练习入口：</p>

    <ul>
      <li><NuxtLink to="/">📗 Day 1 - Nuxt 页面显示</NuxtLink></li>
      
      <li><NuxtLink to="/day3">📙 Day 3 - v-model 双向绑定</NuxtLink></li>
      <!-- 后续可以继续添加 Day 4, 5 等 -->
    </ul>
  </div>
</template>
<script setup>
import { ref } from 'vue'
const count = ref(0)
function increment() {
  count.value++
}
</script>