<script setup>
</script>
<template>

  <div class="block-header">
    <h1 class="block-header__title">
      <span class="block-header__subtitle">
        Reliable, efficient delivery
      </span>
      Powered by Technology
    </h1>
    <p class="block-header__description">
      Our Artificial Intelligence powered tools use millions of project data points
      to ensure that your project is successful
    </p>
  </div>


</template>
<style lang="scss" scoped>
@use "../assets/styles/abstracts" as *;

.block-header {
  margin: 0 auto;
  margin-bottom: fluid(60, 72, 375, 768);
  width: 100%;
  max-width: fluid(304, 550, 375, 768);
  text-align: center;

  &__title {
    margin: 0;
    margin-bottom: rem(16);
    font-size: fluid(24, 36, 375, 768);
    font-weight: 600;
    line-height: 1.4;
    color: $grey-500;
  }

  &__subtitle {
    display: block;
    font-size: fluid(25, 37);
    font-weight: 200;
    line-height: 1.2;
    color: $grey-400;
  }

  &__description {
    margin: 0;
    font-weight: 600;
    line-height: 1.4;
    color: $grey-400;
  }
}
</style>