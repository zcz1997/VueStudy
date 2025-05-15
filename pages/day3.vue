<template>
    <div>
        <h1>Day 3</h1>
        <p>This is the third day of Vue.js</p>
        <input type="text" v-model="message" placeholder="请输入你的名字" maxlength="20"/>
        <p v-if="message">你好，{{ message }}</p>
        <p v-else>你还没有输入你的名字</p>
        <button @click="message = ''">清空输入框</button>
        <p>当前输入：{{ message.length }} / 20 字</p>
    </div>
</template>

<script setup>
import { ref,watch } from 'vue'
//限制message最长10个字
const message = ref('')
watch(message, (newVal, oldVal) => {
        if (newVal.length > 20) {
            message.value = newVal.slice(0, 20)
            alert('最多只能输入20个字')
            }
    }
    )


</script>
