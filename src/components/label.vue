<template>
    <p>
        <strong>{{ label }}</strong> :
        <span v-if="value != ''">{{ value }}</span>
        <span v-else>{{ unknown }}</span>
    </p>
</template>

<script setup>
const unknown = "Inconnu";

const props = defineProps({
    label: String,
    value: {
        type: String,
        default: unknown,
    },
});
</script>

<style scoped>
card{
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 10px
}
</style>