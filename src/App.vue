<template>
  <div class="container">
    <div class="left">
      <template v-for="dragon in dragons">
        <card
            @click="selectedDragon = dragon" 
            :isActive="selectedDragon === dragon"
            :img="dragon.img"
            :name="dragon.name"
            />
      </template>
    </div>
    <div class="right">
      <Zoom v-if="selectedDragon != null" :dragon="selectedDragon" />
    </div>
  </div>
</template>

<script setup>
import Zoom from "@/components/Zoom.vue";
import card from "@/components/card.vue";
import { ref, onMounted } from "vue";

const selectedDragon = ref(null) ;

const url = "https://img.att.ovh/dragons/dragons.json";

const dragons = ref([]);

onMounted(async () => {
  const response = await fetch(url);
  const data = await response.json();
  console.table(data);
  dragons.value = data;
});
</script>

<style scoped>
.left {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20px;
}

.container {
  display: grid;
  grid-template-columns: 50% 50%;
  grid-gap: 20px;
}

</style>





