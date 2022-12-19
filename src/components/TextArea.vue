<script setup>
import { inject } from 'vue';

    const props = defineProps({
        name: {
            type: String,
            required: true
        }
    })

    let values = inject('values');
</script>

<template>
    <textarea :name="props.name" v-model="values[props.name]"></textarea>
</template>

<style scoped>
</style>
