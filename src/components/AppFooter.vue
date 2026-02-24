<template>
  <footer class="attribution">
    <small>
      <span class="attribution__text">
        Challenge by
      </span>
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor.</a>
      <span class="attribution__text">
        Coded by
      </span>
      <a href="https://www.frontendmentor.io/profile/gsnezana7" target="_blank">Snezana</a>
    </small>
  </footer>
</template>
<style lang="scss" scoped>
@use "../assets/styles/abstracts" as *;

.attribution {
  @include site-footer;

  padding-bottom: rem(20);
}
</style>