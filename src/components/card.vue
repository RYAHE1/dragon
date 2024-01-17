<template>
    <figure :class="{ current: isActive }">
        <img :src="img" :alt="name" />
        <figcaption>{{ name }}</figcaption>
    </figure>
</template>

<script setup>
const props = defineProps({
    img: {
        type: String,
    },
    name: {
        type: String,
    },
    isActive: {
        type: Boolean,
        default: false,
    },
});
</script>

<style scoped>
figure {
    margin: 0;
    padding: 0;
    text-align: center;
}

figure img {
    width: 100%;
    border-radius: 50%;
    object-fit: cover;
    border: 5px solid black;
    border-radius: 50%;
}

figure.current img {
    border: 5px solid red;
}
</style>