<template>
    <div v-for="maison in maisons" :key="maisons.nom">
        <card class="w-1/3 p-5" v-bind="maisons" />
    </div>
</template>

<script setup lang="ts">
import card from "../components/card.vue";

const maisons = { nom: "Maison avec vue sur mer", price: 1750, image: "/public/house4.png" }
</script>