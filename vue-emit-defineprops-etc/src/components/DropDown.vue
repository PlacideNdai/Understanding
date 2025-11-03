<template>
    <div>
        <select name="Tea types" id="tea-types" @change="handleSelected($event.target.value)">
            <option value="chai">Chai</option>
            <option value="black-tea">Black Tea</option>
            <option value="green-tea">Green Tea</option>
            <option value="herbal-tea">Herbal Tea</option>
            <option value="oolong-tea">Oolong Tea</option>
            <option value="pu-erh">Pu-erh</option>
        </select>
    </div>
</template>

<script setup>
import { defineEmits } from 'vue';
    const emits = defineEmits(['selectedOption']);

    function handleSelected(value){
        emits('selectedOption', value);
    }
</script>

<style scoped>

</style>