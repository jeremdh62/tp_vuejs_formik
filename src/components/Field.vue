<script setup>
import { inject } from 'vue';

    const props = defineProps({
        type: {
            type: String,
            required: false
        },
        name: {
            type: String,
            required: true
        },
        as: {
            type: String,
            required: false
        }
    })

    let values = inject('values');
    let errors = inject('errors');

    console.log(values);
</script>

<template>
    <div class="field">
        
    </div>
</template>

<style scoped>
</style>
