<script setup>
import {ref, reactive} from 'vue'
import SingleItem from './SingleItem.vue'
import SingleItemY from './SingleItemY.vue'

defineProps(['person'])



</script>


<template>

    <!-- {{ person }} -->
    <div class="flex flex-col">
        <label for="">Name:</label>
        <input type="text" v-model="person.name">
    </div>
    <div class="flex flex-col">
        <label for="">Age:</label>
        <input type="text" v-model="person.age">
    </div>
    <div class="flex flex-col">
        <label for="">Address:</label>
        <input type="text" v-model="person.address">
    </div>
    <div class="bg-red-200 flex flex-col justify-start items-start">
        <SingleItem v-model="person.age" label="Age" class="p-2 w-full"/>
        <SingleItemY v-model="person.address" label="Address"  class="p-2 w-full"/>
    </div>
        


</template>

<style scoped>

</style>
