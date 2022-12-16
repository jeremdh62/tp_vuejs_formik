<script setup>
 const props = defineProps({
     type: {
         type: String,
         required: true
     },
     name: {
         type: String,
         required: false
     },
     values: {
         type: Object,
         required: false
     }
 })

 let value = props.values[props.name];
</script>

<template>
    <input :name="name" :type="type" :value="value"  />
</template>

<style scoped>
</style>
