<script setup>
import { ref, reactive } from 'vue'

defineProps(['message'])

// Define an emitted event called messageEmitted 
// in the ChildComponent using defineEmits.
const emit = defineEmits(['messageEmitted'])

const message_count = ref(1)

// When a button is clicked in the ChildComponent, 
// emit the messageEmitted event along with a custom message.
const buttonClick = () => {
    emit('messageEmitted', `Custom message count is ${message_count.value}`)
    // increase message_count variable to format a custom message
    // everytime when we press click
    message_count.value = message_count.value + 1
}
</script>


<template>
    <div class="m-5 p-2 flex flex-col justify-center items-center 
        rounded-xl border-2 border-gray-200">
        <h1 class="text-2xl font-bold mb-5 text-teal-700 p-2 border-b-4">ChildComponent.vue</h1>
        <div class="flex justify-center items-center m-5">
            <div class="sm:w-1/2 p-10  bg-gray-200 flex flex-col justify-start items-start h-screen">
                <span>Message from Parent:</span>
                <p class="bg-white text-black  text-center mt-5 p-10 rounded-3xl break-words">
                    <!-- In the ChildComponent, 
                    display the received message from the parent component. 
                -->
                    {{ message }}
                </p>
            </div>
            <div class="sm:w-1/2 flex flex-col justify-start items-center h-screen border-2">
                <div class="m-10 bg-white text-gray-700 italic p-2 rounded-3xl text-center">
                    When user click on the button, it will emit the
                    `messageEmitted` event along with this custom message "{{ `Custom message count is ${message_count}` }}"
                </div>
                <div class="sm:w-1/2 sm:pl-10">
                    <button class="mt-5 px-4 py-2 bg-blue-600 text-white 
                ring-4 ring-purple-400
                rounded-md m-2 hover:bg-blue-300 hover:text-gray-600 hover:ring-0" @click="buttonClick">Click</button>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped></style>
