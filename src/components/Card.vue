<template>
  <li class="card" v-for="card in arrayCard" :key="card.name">
    <img :src="card.src" :alt="card.alt" class="card-img" />
    <p><span class="bold">Name:</span> {{ card.name }}</p>
    <p><span class="bold">Age:</span> {{ card.age }}</p>
  </li>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "Card",
  props: {
    arrayCard: Array,
  },
  setup() {
    return {};
  },
});
</script>

<style scoped>
.card {
  width: calc(100% / 2 - 10px);
  background: #f0f2ff;
  box-shadow: 1px 2px 8px #6059704a;
  border-radius: 8px;
  padding: 10px;
}

.card-img {
  border-radius: 8px;
}
</style>