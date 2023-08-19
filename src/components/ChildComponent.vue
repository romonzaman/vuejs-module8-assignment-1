<script setup>
import {ref, reactive} from 'vue'

defineProps(['message'])
const emit = defineEmits(['messageEmitted'])

const message_count = ref(1)

const buttonClick = ()=>{
    emit('messageEmitted', `Custom message count is ${message_count.value}`)
    message_count.value = message_count.value + 1
}
</script>


<template>

    <div class="m-5 p-2 bg-gray-400 text-white w-1/2 flex flex-col justify-center items-center 
        rounded-xl shadow-2xl">
        <h1 class="text-2xl font-bold m-5 bg-white text-teal-700 p-2 border-b-4">ChildComponent.vue</h1>
        <span>Message from Parent:</span>
        <p class="bg-white text-black w-full text-center mt-5 p-10 rounded-3xl">
            {{ message }}
        </p>
        <div class="flex flex-col justify-center items-center sm:flex-row">
            <div class="sm:w-1/2 m-10 bg-white text-gray-700 italic p-2 rounded-3xl text-center" >
                When user click on the button, it will send emit then
                `messageEmitted` event along with this custom message "{{ `Custom message count is ${message_count}` }}"
            </div>
            <div class="sm:w-1/2 sm:pl-10">
                <button 
                class="mt-5 px-4 py-2 bg-blue-600 text-white 
                ring-4 ring-purple-400
                rounded-md m-2 hover:bg-blue-300 hover:text-gray-600 hover:ring-0"
                @click="buttonClick">Click</button>
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>
