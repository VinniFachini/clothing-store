<template>
  <div class="announcement">
    <div class="announcement__image">
      <img :src="imageSrc" :alt="title" />
    </div>
    <div class="announcement__title">{{ title }}</div>
    <div class="announcement__text">{{ text }}</div>
  </div>
</template>

<script>
export default {
  props: {
    imageSrc: String,
    text: String,
    title: String,
  },
};
</script>

<style lang="scss" scoped>
.announcement {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  flex-basis: 250px;
  &__image {
    width: 100%;
    max-width: 35px;
    img {
      max-width: 35px;
    }
  }
  &__title {
    font-size: 1.125rem;
    font-weight: 700;
  }
  &__text {
    color: #737373;
    text-align: center;
  }
}
</style>