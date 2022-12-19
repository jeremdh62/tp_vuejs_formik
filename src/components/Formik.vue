<script setup>
import { provide, ref } from 'vue';

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

    let values = ref(props.initialValues);

    let errors = props.validate(values.value);

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