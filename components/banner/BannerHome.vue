<template>
  <Carousel :autoplay="8000" :wrap-around="true" :transition="1000">
    <Slide v-for="slide in 10" :key="slide">
      <div class="carousel__item">
        <img src="https://via.placeholder.com/1920x630" alt="Banner" />
      </div>
    </Slide>

    <template #addons>
      <Navigation />
      <Pagination />
    </template>
  </Carousel>
</template>

<style lang="scss">
.carousel__pagination {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    bottom: 20px;
}
.carousel__pagination-button::after{
    width: 12px !important;
    height: 12px !important;
    border-radius: 50% !important;
}
</style>