<template>

    <card class="w-1/2" v-bind="objet" />

</template>

<script setup lang="ts">

import card from "../components/card.vue";

const objet = { nom: "maison avec vue sur mer", price: 1350 }

</script>