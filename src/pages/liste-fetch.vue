<template>
    <div v-for="maison in maisons" :key="maisons.nom">
        <card class="w-1/2" v-bind="maisons" />
    </div>
</template>

<script setup lang="ts">

import card from "../components/card.vue";
const res = await fetch("maisons.json");
const maisons = await res.json();

</script>