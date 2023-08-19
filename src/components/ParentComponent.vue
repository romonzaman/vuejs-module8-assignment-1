<script setup>
import {ref, reactive} from 'vue'
import ChildComponent from './ChildComponent.vue'

defineProps(['message'])

const messageData = ref('')
const messageEmitted = (message) => {
    messageData.value = message
    console.log(message)
}

</script>


<template>


    <div class="h-screen">
        <div class="flex flex-col justify-center items-center">

            <h1 class="text-3xl mt-10 shadow-sm shadow-blue-300 border-b-2">ParentComponent.vue</h1>
            <h2 class="mt-5">messageEmitted (by Child):</h2>
            <p class="text-md m-2 font-bold italic shadow-lg shadow-purple-400 p-2 h-10">
                {{ messageData }}
            </p>
            <ChildComponent :message="message" @message-emitted="messageEmitted" />
        </div>
    </div>

</template>

<style scoped>

</style>
