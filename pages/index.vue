<template>
  <Head>
    <Title>Clothing Store Online - Your place to online purchases</Title>
    <Meta name="description" content="An Online Clothing Store" />
  </Head>
  <BannerHome />
  <BannerAnnouncements />
  <BannerGrid
    first="https://via.placeholder.com/960x960"
    second="https://via.placeholder.com/800x400"
    third="https://via.placeholder.com/800x400"
    fourth="https://via.placeholder.com/800x400"
    title="Banner Grid"
  />
  <ProductShowcase title="Best Sellers" :products="products"/>
</template>


<script>
export default {
  setup() {
    
  },
  data() {
    return {
      products: []
    }
  },
  mounted() {
    this.fetchProducts('../api.json')
  },
  methods: {
    fetchProducts: async function(url) {
      const info = await fetch(url)
      const infoJson = await info.json()
      this.products = infoJson.products
    }
  }
}
</script>


<style lang="scss" scoped>
.carousel__slide {
  display: block !important;
}
</style>