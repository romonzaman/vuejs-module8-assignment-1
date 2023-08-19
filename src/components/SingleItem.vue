<script setup>
import { ref, reactive } from 'vue';

defineProps(['modelValue', 'label'])
defineEmits(['update:modelValue'])
</script>


<template>
    <div class="flex flex-col">
        <label for="">{{ label }}:</label>
        <input type="text" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)">
    </div>
</template>

<style scoped></style>
