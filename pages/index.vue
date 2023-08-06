<template>
  <Head>
    <Title>Clothing Store Online - Your place to online purchases</Title>
    <Meta name="description" content="An Online Clothing Store" />
  </Head>
  <BannerHome :banners="bannerHomeItems" />
  <BannerAnnouncements />
  <BannerGrid :banners="bannerGridItems" title="Banner Grid" />
  <ProductShowcase title="Best Sellers" :products="products" />
  <ProductShowcase title="Snickers" :products="products" />
  <BannerFull  :banners="bannerFullItems" title="They wear us" />
  <ProductShowcase title="Accessories" :products="products" />
  <ProductShowcase title="Shirts" :products="products" />
  <Newsletter />
  <BannerAboutUs :banners="bannerAboutUs"/>
</template>


<script>
export default {
  setup() {},
  data() {
    return {
      products: [],
      bannerHomeItems: [],
      bannerGridItems: [],
      bannerFullItems: [],
      bannerAboutUs: []
    };
  },
  mounted() {
    this.fetchProducts("../api.json");
    this.fetchBannerHome("../api.json");
    this.fetchBannerGrid("../api.json");
    this.fetchBannerFull("../api.json");
    this.fetchBannerAboutUs("../api.json")
  },
  methods: {
    fetchProducts: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.products = infoJson.products;
    },
    fetchBannerHome: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.bannerHomeItems = infoJson.banners.bannerHome;
    },
    fetchBannerGrid: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.bannerGridItems = infoJson.banners.bannerGrid;
    },
    fetchBannerFull: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.bannerFullItems = infoJson.banners.bannerFull;
    },
    fetchBannerAboutUs: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.bannerAboutUs = infoJson.banners.bannerAboutUs;
    },
  },
};
</script>


<style lang="scss" scoped>
.carousel__slide {
  display: block !important;
}
</style>