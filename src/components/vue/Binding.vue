<script setup>

import {ref , computed} from 'vue';
const text = ref('hola mundo');
const checked = ref(true);

// const message = computed(()=>{
//     return checked.value ? 'Apagar' : 'Encender'
// })

const message = computed (()=>{
    let message;
    if(checked.value){
        message = 'Apagar';
    }else{
        message = 'Encender';
    }
    return message;
})
const items = ["Hola","Mundo"]
</script>

<template>

    <ul>
        <li v-for="(text,index) in items" :key="index">
            {{ text }}
        </li>
    </ul>

    <div class="bg-blue-400 inline-block text-white rounded py-1 px-2" :class="{'bg-orange-400' : checked}">
		Hola mundo
	</div>
    <div>
        <input type="checkbox" id="checkbox" v-model="checked" />
	<!-- <label for="checkbox">{{ checked ? 'Apagar' : 'encender' }}</label> -->
        <label for="checkbox">{{ message }}</label>
    </div>
	<div>
		<input class="border-gray-300 border-2" v-model="text">
	</div>
    {{ text }}
</template>
