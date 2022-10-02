<script setup lang="ts">
import { supabase } from "@/supabase"
import { ref } from "@vue/reactivity";
import Card from "./card.vue";

import { useRouter } from "vue-router";
const router = useRouter();

const maison = ref({});



const props = defineProps(["id"]);
if (props.id) {
    // On charge les données de la maison
    let { data, error } = await supabase
        .from("Maison")
        .select("*")
        .eq("id", props.id);
    if (error) console.log("n'a pas pu charger le table Maison :", error);
    else maison.value = (data as any[])[0];
}

async function upsertMaison(dataForm, node) {
    const { data, error } = await supabase.from("Maison").upsert(dataForm);
    if (error) node.setErrors([error.message])
    else {
        node.setErrors([]);
        router.push({ name: "edit-id", params: { id: data[0].id } });
    }
}
</script>

<template>
    <div>
        <div class="p-2">
            <h2 class="text-2xl">Résultat (Prévisualisation)</h2>
            <Card v-bind="maison" />
        </div>
        <div class="p-2">
            <FormKit @submit="upsertMaison" type="form" v-model="maison" submit-label="Changer"
                :submit-attrs="{ classes: { input: 'bg-indigo-300 p-1 rounded' } }"
                :config="{ classes: { input: 'p-1 rounded border-black-600 shadow-sm border', label: 'text-gray-600',},}">

                <FormKit name="nom" label="Nom" />
                <FormKit name="price" label="Prix du bien" type="number" />
                <FormKit name="adresse" label="Adresse"/>
                <FormKit name="nbrSDB" label="Nombre de salle de bains" type="number"/>
                <FormKit name="nbrChambres" label="Nombre de chambres" type="number"/>
                <FormKit name="surface" label="Superficie" />
                <FormKit name="image" label="Image" />
                <br />
            </FormKit>
        </div>
    </div>
</template>