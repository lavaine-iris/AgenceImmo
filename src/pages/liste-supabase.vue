<script setup lang="ts">

    import card from "../components/card.vue";
    import { supabase } from "../supabase";
    console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code
    
     
    const { data: Maison, error } = await supabase
    
        .from('Maison')
        .select('*')
    const maison = Maison;
    
    console.log("Maison:", Maison);

 

    
</script>
    
<template>
    <div v-for="maison in Maison" :key="maison.nom">
        <card class="w-1/2 p-5" v-bind="maison" />
    </div>
</template>

