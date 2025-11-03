<template>
    <div v-if="isShow">
        <!-- <h1>Selected Tea Type: {{ teaData }}</h1> -->
        <p>{{ teaData }}</p>
        <button @click="handleClose">Close</button>
    </div>
</template>

<script setup>
import { defineEmits, defineProps } from 'vue';

    const props = defineProps(['isShow', 'teaData', 'selectedOption']);
    const emits = defineEmits(['isShow'])

    function handleClose(){
        emits('isShow');
    }

</script>

<style scoped>
div {
    background: lightgray;
}
</style>