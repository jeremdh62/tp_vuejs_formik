<script setup>
import { inject } from 'vue';
import Select from './Select.vue';
import Input from './Input.vue';
import TextArea from './TextArea.vue';

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
</script>

<template>
    <div v-if="as">
        <div v-if="as === 'Select'" >
            <Select :name="name" :values="values" />
        </div>
        <div v-if="as === 'TextArea'" >
            <TextArea :name="name" :values="values" />
        </div>
    </div>
    <div v-else>
        <Input :name="name" :type="type" />
    </div>
</template>

<style scoped>
</style>
