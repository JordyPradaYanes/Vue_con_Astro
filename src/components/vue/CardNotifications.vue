<script setup>
import { ref } from 'vue';
const counter = ref(0);

function decrement() {
    if (counter.value > 0) {
        counter.value--
    }
}
function increment() {
    counter.value++
}
</script>

<template>
    <div class="flex-col bg-slate-200 rounded py-8 px-6 w-96 shadow-md flex items-center">
        <div class="relative mb-6">
            <img class="rounded-full size-32"
                src="https://pbs.twimg.com/profile_images/1600219064869298177/lhnutETN_400x400.jpg" alt="">
            <div v-show="counter > 0"
                class="absolute top-0 right-0 flex justify-center items-center size-6 rounded-full bg-red-500 text-white">
                {{ counter }}
            </div>
            <div v-show="counter > 0"
                class="absolute top-0 left-0 flex justify-center items-center size-6 rounded-full bg-red-500 text-white">
                {{ counter }}
            </div>
        </div>
        <p v-if="counter > 0">Tienes nuevos mensajes, Burry!
            😁
        </p>
        <p v-else>Nadie te habla, Cachón 😔</p>
        <div class="flex justify-around w-24 mt-6">
            <button @click="decrement" class="bg-blue-200 rounded w-6 flex justify-center items-center px-2">-</button>
            {{ counter }}
            <button @click="increment" class="bg-blue-200 rounded w-6 flex justify-center items-center px-2">+</button>
        </div>
    </div>
</template>