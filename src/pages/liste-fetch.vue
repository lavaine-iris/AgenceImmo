<template>
    <div v-for="maison in maisons" :key="maison.nom">
        <card class="w-1/2 p-5" v-bind="maison" />
    </div>
</template>

<script setup lang="ts">

import card from "../components/card.vue";
const res = await fetch("/public/maisons.json");
const maisons = await res.json();

</script>