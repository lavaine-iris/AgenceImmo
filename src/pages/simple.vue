<template>

    <card class="w-1/2 p-5" v-bind="objet" />

</template>

<script setup lang="ts">

import card from "../components/card.vue";

const objet = {
    nom: "Maison avec vue sur mer",
    price: 1350,
    image: "/public/house6.png"
}
</script>