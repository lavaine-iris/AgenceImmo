<template>
    <div v-for="maison in maisons" :key="maison.nom">
        <card class="w-1/3 p-5" v-bind="maison" />
    </div>
</template>

<script setup lang="ts">

import card from "../components/card.vue";
import { supabase } from "../supabase";
console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code
const maisons = []; // à remplacer par l'appel à Supabase

</script>