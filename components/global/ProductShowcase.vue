<template>
  <div class="container showcase">
    <h2 class="showcase__title">{{ title }}</h2>
    <ul class="products-container">
      <Carousel v-bind="settings" :breakpoints="breakpoints">
        <Slide v-for="slide in products" :key="slide.id">
          <Product
            :title="slide.name"
            :oldPrice="slide.oldPrice"
            :newPrice="slide.newPrice"
            :images="slide.images"
            :sku="slide.sku"
          />
        </Slide>
      </Carousel>
    </ul>
  </div>
</template>

<style lang="scss" scoped>

.carousel__slide{
  display: flex;
  align-items: flex-start;
}
.showcase {
  margin-bottom: 40px;
  &__title {
    font-size: 2rem;
    text-transform: uppercase;
    font-weight: 400;
    text-align: center;
    margin-bottom: 30px;
  }
}
</style>

<script>
export default {
  setup() {},
  props: {
    title: String,
    products: Object,
  },
  data() {
    return {
      settings: {
        itemsToShow: 1,
        snapAlign: "start",
        wrapAround: true,
      },
      breakpoints: {
        525: {
          itemsToShow: 2
        },
        768: {
          itemsToShow: 3
        },
        1280: {
          itemsToShow: 4
        }
      }
    };
  },
};
</script>