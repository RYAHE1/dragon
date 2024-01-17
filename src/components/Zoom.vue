<template>
    <h1>{{ dragon.name }}</h1>
    <p>{{ dragon.behavior }}</p>
    <p><img :src="dragon.img" :alt="dragon.name" /></p>

    <Label label="Trésor" :value="dragon.treasure" />
    <Label label="Couleur" :value="dragon.color" />
    <Label label="Espérance de cie" :value="dragon.life_expectancy.toString()" />
    <Label label="Alimentation" :value="dragon.alimentation" />
    <Label label="Taille" :value="dragon.size.toString()" />
    <Label label="Habitat" :value="dragon.habitat" />
</template>

<script setup>
import Label from "@/components/Label.vue";

const props = defineProps({
    dragon: {
        type: Object,
    },
});
</script>