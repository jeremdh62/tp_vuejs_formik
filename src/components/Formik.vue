<script setup>
import { provide } from 'vue';

    const props = defineProps({
        initialValues: {
            type: Object,
            required: true
        },
        validate: {
            type: Function,
            required: true
        },
    })

    let isSubmitting = false;

    function handleSubmit() {
        isSubmitting = true;
    }

    function values() {
        return  {};
        //return props.initialValues;
    }

    function errors() {
        return {};
    }

    provide('values', values);
    provide('errors', errors);
</script>

<template>
    <slot 
        :isSubmitting="isSubmitting"
        :handleSubmit="handleSubmit"
        :values="values"
        :errors="errors"
    >
    </slot>
</template>

<style scoped>
</style>