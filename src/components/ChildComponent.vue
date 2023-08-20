<script setup>
import { defineProps } from 'vue';

defineProps(['person', 'messageToChild', 'messageFromChild'])
defineEmits(['update:messsageFromChild'])
</script>
<template>
    <div class="p-5 border-2 border-gray-300 border-s-fuchsia-50">
        <div class="max-w-lg mx-auto p-4 bg-white rounded-md shadow-md flex flex-col items-center justify-center mb-5">
            <h1 class="text-xl font-bold text-gray-900">
                {{ messageToChild }}
            </h1>
        </div>

        <div class="max-w-md mx-auto p-10 bg-white rounded-md shadow-md flex flex-col items-center justify-center">
            <img class="w-20 h-20 rounded-full ring-4 ring-sky-600" src="https://images.unsplash.com/photo-1606041008023-472dfb5e530f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=688&q=80" alt="Mehedi  Jaman's Photo">
            <div class="flex flex-col items-center justify-center pt-5 pb-5">
                <p class="text-lg font-semibold">{{ person.name }}</p>
                <p class="text-sm text-gray-500">{{ person.title }}</p>
            </div>
            <div class="flex gap-2">
                <button @click="$emit('update:messageFromChild',person.url)" class="bg-sky-500 py-1 px-4 rounded-3xl text-white font-bold hover:bg-sky-600 hover:text-gray-100">See Portfolio</button>
                <button @click="$emit('update:messageFromChild','')" class="bg-sky-500 py-1 px-4 rounded-3xl text-white font-bold hover:bg-sky-600 hover:text-gray-100">Hide Portfolio</button>
            </div>
        </div>
    </div>
</template>