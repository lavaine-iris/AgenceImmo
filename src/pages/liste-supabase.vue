<script setup lang="ts">

    import card from "../components/card.vue";
    import { supabase } from "../supabase";
    console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code
    const maison = [supabase];
     
    const { data: listeDesMaisons, error } = await supabase
    
        .from('Maison')
        .select('*')
    
    console.log("Maison:", listeDesMaisons);
    
</script>
    
<template>
    <div v-for="maison in listeDesMaisons" :key="maison.nom">
        <card class="w-1/2 p-5" v-bind="maison" />
    </div>
</template>

