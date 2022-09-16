<script setup lang="ts">
import maisons from "public/maisons.json";
import Card from "../../components/card.vue"
defineProps<{ nbr: string }>();
</script>

<template>
    <div>
        <Card v-bind="maisons[Number(nbr)]" />
    </div>
</template>