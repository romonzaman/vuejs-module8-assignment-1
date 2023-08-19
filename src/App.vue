<script setup>

import { ref, reactive } from 'vue'

import ParentComponent from './components/ParentComponent.vue'

const message = ref("Hello World!")

</script>


<template>

    <div class="flex flex-col justify-center items-center">
        <h1 class="border-b-4">App.vue</h1>
        <input type="text" v-model="message" placeholder="Enter Message">
        <ParentComponent :message="message" />
    </div>
</template>

<style scoped>
</style>
