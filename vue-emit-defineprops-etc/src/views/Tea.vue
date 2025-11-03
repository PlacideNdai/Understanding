<template>

    <div>
        <h4>Select Tea to learn more about it.</h4>
        <DropDown @selected-option="handleSelected" />
        <Popup :is-show="isShow" @is-show="isShow = false" :tea-data="teaData"/>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import DropDown from '../components/DropDown.vue';
import Popup from '../components/Popup.vue';

// Tea info.
const teaTypes = ref({
        "chai": "Minimally processed with delicate flavor; highest in antioxidants and lowest in caffeine among true teas.",
        "black-tea": "Unoxidized and steamed or pan-fired; known for grassy flavor and high catechin content, which may support metabolism.",
        "green-tea": "Rare and lightly fermented; smoother than green tea with a mellow taste and gentle aroma.",
        "oolong-tea": "Partially oxidized, ranging from light to dark; complex flavor profile and may aid digestion and heart health.",
        "pu-erh": "Fully oxidized; bold flavor and highest caffeine among true teas; may support alertness and heart health.",
        "pu-erh-tea": "Fermented and aged; earthy flavor and probiotic potential; traditionally used for cholesterol and weight management.",
        "herbal-tea": "Not from Camellia sinensis; includes blends like chamomile, peppermint, and rooibos; caffeine-free and often used for relaxation or digestion."
    })

const selectedTea = ref(null);
const isShow = ref(false);
let teaData = ref(null);


const handleSelected = (event) =>{
    selectedTea.value = event;
    teaData = teaTypes.value[event];

    isShow.value = true;
}


</script>

<style scoped></style>