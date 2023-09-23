<template>
  <Head>
    <Title>Clothing Store Online - Your place to online purchases</Title>
    <Meta name="description" content="An Online Clothing Store" />
  </Head>
  <BannerHome :banners="bannerHomeItems" />
  <BannerAnnouncements />
  <BannerGrid :banners="bannerGridItems" title="Banner Grid" />
  <ProductShowcase :title="firstShowcase.title" :products="firstShowcase.products" />
  <ProductShowcase :title="secondShowcase.title" :products="secondShowcase.products" />
  <BannerFull  :banners="bannerFullItems" title="They wear us" />
  <ProductShowcase :title="thirdShowcase.title" :products="thirdShowcase.products" />
  <ProductShowcase :title="fourthShowcase.title" :products="fourthShowcase.products" />
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
      bannerAboutUs: [],
      firstShowcase: [],
      secondShowcase: [],
      thirdShowcase: [],
      fourthShowcase: [],
    };
  },
  mounted() {
    this.fetchProducts("../api.json");
    this.fetchfirstShowcase("../api.json");
    this.fetchsecondShowcase("../api.json");
    this.fetchthirdShowcase("../api.json");
    this.fetchfourthShowcase("../api.json");
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
    fetchfirstShowcase: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.firstShowcase = infoJson.showcases[0];
    },
    fetchsecondShowcase: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.secondShowcase = infoJson.showcases[1];
    },
    fetchthirdShowcase: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.thirdShowcase = infoJson.showcases[2];
    },
    fetchfourthShowcase: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.fourthShowcase = infoJson.showcases[3];
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