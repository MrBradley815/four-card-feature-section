<script setup>
import { ref } from 'vue';
import CardItem from './CardItem.vue';
import iconSupervisor from '@/assets/icons/icon-supervisor.svg';
import iconTeamBuilder from '@/assets/icons/icon-team-builder.svg';
import iconKarma from '@/assets/icons/icon-karma.svg';
import iconCalculator from '@/assets/icons/icon-calculator.svg';

const cardList = ref([
  {
    id: 0,
    title: 'Supervisor',
    text: 'Monitors activity to identify project roadblocks',
    color: 'inset-shadow-[0_4px_0_0_var(--color-cyan)]',
    icon: iconSupervisor,
    iconTitle: 'Magnifying glass icon',
    area: 'supervisor',
  },
  {
    id: 1,
    title: 'Team Builder',
    text: 'Scans our talent network to create the optimal team for your project',
    color: 'inset-shadow-[0_4px_0_0_var(--color-red)]',
    icon: iconTeamBuilder,
    iconTitle: 'Webpage icon',
    area: 'team',
  },
  {
    id: 2,
    title: 'Karma',
    text: 'Regularly evaluates our talent to ensure quality',
    color: 'inset-shadow-[0_4px_0_0_var(--color-orange)]',
    icon: iconKarma,
    iconTitle: 'Lightbulb icon',
    area: 'karma',
  },
  {
    id: 3,
    title: 'Calculator',
    text: 'Uses data from past projects to provide better delivery estimates',
    color: 'inset-shadow-[0_4px_0_0_var(--color-blue)]',
    icon: iconCalculator,
    iconTitle: 'Computer monitor icon',
    area: 'calculator',
  },
]);
</script>

<template>
  <div class="cards-grid grid gap-8">
    <CardItem v-for="card in cardList" :key="card.id" :card :style="{ gridArea: card.area }" />
  </div>
</template>

<style scoped>
.cards-grid {
  grid-template-areas: 'supervisor' 'team' 'karma' 'calculator';
}

@media (width >= 40rem) {
  .cards-grid {
    grid-template-columns: repeat(4, 1fr);
    grid-template-areas:
      '.          team       team       .    '
      'supervisor supervisor karma      karma'
      '.          calculator calculator .    ';
  }
}

@media (width >= 64rem) {
  .cards-grid {
    grid-template-columns: repeat(3, 1fr);
    grid-template-areas:
      '.          team  .         '
      'supervisor team  calculator'
      'supervisor karma calculator'
      '.          karma .         ';
  }
}
</style>
