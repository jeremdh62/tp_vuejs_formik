<script setup>
import { inject } from 'vue';

 const props = defineProps({
     type: {
         type: String,
         required: true
     },
     name: {
         type: String,
         required: false
     }
 })


 let values = inject('values');

</script>

<template>
    <input :name="name" :type="type" v-model="values[props.name]" />
</template>

<style scoped>
</style>
