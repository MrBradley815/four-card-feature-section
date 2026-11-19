<script setup>
defineProps(['card']);
</script>

<template>
  <div class="bg-white p-8 rounded-lg shadow-[0_15px_30px_-11px_rgba(131,166,210,0.5)] inset-ring-cyan" :class="card.color">
    <h3 class="text-preset-3 text-gray-500 mb-1.5">{{ card.title }}</h3>
    <p class="text-preset-5 text-gray-400 mb-8">{{ card.text }}</p>
    <img :src="card.icon" class="ms-auto mb-3.75" :alt="card.iconTitle" />
  </div>
</template>
