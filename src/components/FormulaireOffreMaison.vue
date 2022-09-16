<script setup lang="ts">
import { ref } from "@vue/reactivity";
import Card from "./card.vue";
const maison = ref({});
</script>

<template>
    <div>
        <div class="p-2">
            <h2 class="text-2xl">Résultat (Prévisualisation)</h2>
            <Card v-bind="maison" />
        </div>
        <div class="p-2">
            <FormKit type="form" v-model="maison" :submit-attrs="{ classes: { input: 'bg-indigo-300 p-1 rounded' } }"
                :config="{
                classes: {
                input: 'p-1 rounded border-black-600 shadow-sm border',
                label: 'text-gray-600',
                },
                }">
                <FormKit name="nom" label="Nom" />
                <FormKit name="price" label="Prix du bien" type="number" />
                <FormKit name="favori" label="Mettre en valeur" type="checkbox" wrapper-class="flex" />
            </FormKit>
        </div>
    </div>
</template>