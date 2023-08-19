<script setup>
import { ref, reactive, computed } from 'vue';

const props = defineProps(['modelValue', 'label'])
const emit = defineEmits(['update:modelValue'])

const value = computed({
    get() {
        return props.modelValue
    },
    set(value) {
        emit('update:modelValue', value)
    }
})
</script>


<template>
    <div class="flex flex-col">
        <label for="">{{ label }}:</label>
        <input type="text" v-model="value">
    </div>
</template>

<style scoped></style>
