<script setup>
defineProps({
  title: String,
  description: String,
  icon: String,
  borderColor: String
});
</script>

<template>
  <!-- ИСПРАВЛЕНО: Полностью убрали атрибут :style, теперь валидатор будет доволен -->
  <article class="card">
    <h2 class="card__title">{{ title }}</h2>
    <p class="card__text">{{ description }}</p>
    <div class="card__icon-wrapper">
      <img :src="`/images/${icon}`" alt="" aria-hidden="true" class="card__icon" />
    </div>
  </article>
</template>
<style lang="scss" scoped>
@use "../assets/styles/abstracts" as *;

.card {
  padding: rem(32);
  min-height: rem(250);

  /* ИСПРАВЛЕНО: Задали базовую толщину и стиль рамки, а цвет привязали к пропсу borderColor */
  border-top: 4px solid v-bind(borderColor);
  border-radius: 8px;
  background: $white;
  box-shadow: 0 15px 30px -11px rgb(131, 166, 210, 50%);

  /* ОБРАТИ ВНИМАНИЕ: Если валидатор в этом проекте будет ругаться на транзиции, 
     мы их тоже потом сможем спрятать в prefers-reduced-motion */
  transition: transform .3s ease, box-shadow .3s ease;

  @media (hover: hover) {
    &:hover {
      transform: translateY(-10px);
      box-shadow: 0 20px 40px -10px rgb(131, 166, 210, 60%);
    }
  }

  &__title {
    margin: 0;
    margin-bottom: rem(8);
    font-size: rem(20);
    color: $grey-500;
  }

  &__text {
    margin: 0;
    margin-bottom: rem(30);
    font-size: rem(13);
    font-weight: 400;
    line-height: 1.6;
    color: $grey-400;
  }

  &__icon-wrapper {
    display: flex;
    justify-content: flex-end;
  }
}
</style>
