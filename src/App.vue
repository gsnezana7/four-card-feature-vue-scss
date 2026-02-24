<script setup>
import Header from './components/AppHeader.vue';
import Footer from './components/AppFooter.vue';
import AppCard from './components/AppCard.vue';

const features = [
  {
    id: 1,
    title: 'Supervisor',
    desc: 'Monitors activity to identify project roadblocks',
    icon: 'icon-supervisor.svg',
    color: 'hsl(180, 62%, 55%)',
    gridArea: 'supervisor'
  },
  {
    id: 2,
    title: 'Team Builder',
    desc: 'Scans our talent network to create the optimal team for your project',
    icon: 'icon-team-builder.svg',
    color: 'hsl(0, 78%, 62%)',
    gridArea: 'builder'
  },
  {
    id: 3,
    title: 'Karma',
    desc: 'Regularly evaluates our talent to ensure quality',
    icon: 'icon-karma.svg',
    color: 'hsl(34, 97%, 64%)',
    gridArea: 'karma'
  },
  {
    id: 4,
    title: 'Calculator',
    desc: 'Uses data from past projects to provide better delivery estimates',
    icon: 'icon-calculator.svg',
    color: 'hsl(212, 86%, 64%)',
    gridArea: 'calc'
  }
];

</script>

<template>
  <section class="container">
    <Header />
    <ul class="features-grid">
      <li v-for="card in features" :key="card.id"
        :class="['features-grid__item', `features-grid__item--${card.gridArea}`]">
        <AppCard :title="card.title" :description="card.desc" :icon="card.icon" :borderColor="card.color" />
      </li>
    </ul>
  </section>

  <Footer />
</template>

<style lang="scss" scoped>
@use "./assets/styles/abstracts" as *;

.container {
  margin: 0 auto;
  padding: rem(30);
  padding-top: fluid(56, 103, 375, 768);
  width: 100%;
  max-width: rem(1440);
}

.features-grid {
  display: grid;
  gap: rem(32);
  padding: 0;
  list-style: none;
  grid-template-columns: 1fr;

  @media (width >=rem(1024)) {
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 1fr);
    align-items: center;
    grid-template-areas: "supervisor builder calc"
      "supervisor karma   calc";

    &__item {
      &--supervisor {
        grid-area: supervisor;
      }

      &--builder {
        grid-area: builder;
      }

      &--karma {
        grid-area: karma;
      }

      &--calc {
        grid-area: calc;
      }
    }
  }
}
</style>
