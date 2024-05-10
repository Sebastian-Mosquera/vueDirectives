<script setup>
import { ref } from 'vue'

const todos =ref (['Estudiar bastante']);
const todo = ref('')

function add(){
    todos.value.unshift(todo.value)
    todo.value=''
}
</script>
<template>
    <div class="py-6 px-5 rounded shadow bg-slate-200 max-w-96 mx-auto mt-10">
        <div>
            <input v-model= "todo" class="px-2 w-4/5 outline-none rounded"/>
            <button @click="add" class="w-1/5 bg-green-500 text-white text-center rounded">
                +
            </button>
        </div>
            <div class="mt-3">
                <div>
                    <div v-for="(todo,i) in todos" :key="i" class="mt-1 px-1 bg-yellow-400 ">{{ todo }}</div>
                </div>
            </div>
    </div>
</template>