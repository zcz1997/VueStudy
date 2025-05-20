<template>
    <div style="padding: 2em;">
        <h1>Day 4</h1>
        <input type="text" v-model="newTask" placeholder="Add a new task" @keyup.enter="addTask"/>
        <button @click="addTask">Add Task</button>
        <ul>
            <li v-for="(task, index) in tasks" :key="index">
                <span @click="toggleDone(index)" :style="{
                    textDecoration: task.done ? 'line-through' : 'none',
                    color: task.done ? 'gray' : 'black',
                    cursor: 'pointer'
                }">
                    ✅ {{ task.text }}
                </span>
                <button @click="removeTask(index)">Delete Task</button>
            </li>
        </ul>
        <p>you can input {{ leftwords }} characters left</p>
        <p v-if="tasks.length === 0">No tasks yet</p>
    </div>
</template>
<script setup>
import { ref, watch } from 'vue'
const tasks = ref([])
const newTask = ref('')
const leftwords = ref(20)
const toggleDone =(index) => {
    tasks.value[index].done = !tasks.value[index].done
}
function addTask() {
    if (newTask.value.trim() === '') {
        return
    }
    tasks.value.push({
        text: newTask.value,
        done: false
    })
    newTask.value = ''
}
const removeTask = (index) => {
    tasks.value.splice(index, 1)
}
watch(newTask, (val) => {
    if (val.length > 20) {
        newTask.value = val.slice(0, 20)
        alert("Task name should be less than 20 characters")
    }
    leftwords.value = 20 - val.length
})

</script>