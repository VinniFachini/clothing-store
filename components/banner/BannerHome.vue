<template>
  <Carousel :autoplay="8000" :wrap-around="true" :transition="1000">
    <Slide v-for="banner in banners" :key="banner">
      <div class="carousel__item">
        <img :src="banner.link" alt="Banner" />
      </div>
    </Slide>

    <template #addons>
      <Navigation />
      <Pagination />
    </template>
  </Carousel>
</template>

<script>
export default {
  setup() {},
  props: {
    banners: Object
  },
};
</script>

<style lang="scss">
.carousel__item {
  width: 100vw;
  img {
    width: 100%;
    @media screen and (max-width: 992px) {
      aspect-ratio: 1 / 1;
      object-fit: cover;
    }
  }
}
.carousel__pagination {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  bottom: 20px;
}
.carousel__pagination-button::after {
  width: 12px !important;
  height: 12px !important;
  border-radius: 50% !important;
}
</style>