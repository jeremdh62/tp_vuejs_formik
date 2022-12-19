<script setup>
import { inject } from 'vue';

    const props = defineProps({
        name: {
            type: String,
            required: true
        },
        values: {
            type: Object,
            required: true
        }
    })

    let values = inject('values');
    let errors = inject('errors');


</script>

<template>
    <select>
        <option v-for="option in values[props.name]" :value="option.value">
            {{ option.label }}
        </option>
    </select>
</template>

<style scoped>
</style>
