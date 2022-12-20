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

    let isSubmitting = ref(false);

    function handleSubmit() {
        isSubmitting.value = true;
        errors = props.validate(values.value);
    }

    let values = ref(props.initialValues);

    let errors = {};

    let validate = ref(props.validate);

    provide('values', values);
    provide('errors', errors);
    provide('validate', validate);
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