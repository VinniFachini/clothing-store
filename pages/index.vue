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
    this.fetchfirstShowcase("http://localhost:3001/showcases");
    this.fetchsecondShowcase("http://localhost:3001/showcases");
    this.fetchthirdShowcase("http://localhost:3001/showcases");
    this.fetchfourthShowcase("http://localhost:3001/showcases");
    this.fetchBannerHome("http://localhost:3001/banners");
    this.fetchBannerGrid("http://localhost:3001/banners");
    this.fetchBannerFull("http://localhost:3001/banners");
    this.fetchBannerAboutUs("http://localhost:3001/banners")
  },
  methods: {
    fetchfirstShowcase: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.firstShowcase = infoJson[0];
    },
    fetchsecondShowcase: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.secondShowcase = infoJson[1];
    },
    fetchthirdShowcase: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.thirdShowcase = infoJson[2];
    },
    fetchfourthShowcase: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.fourthShowcase = infoJson[3];
    },
    fetchBannerHome: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      console.log("Banner Home: ", infoJson)
      this.bannerHomeItems = infoJson.bannerHome;
    },
    fetchBannerGrid: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.bannerGridItems = infoJson.bannerGrid;
    },
    fetchBannerFull: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.bannerFullItems = infoJson.bannerFull;
    },
    fetchBannerAboutUs: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.bannerAboutUs = infoJson.bannerAboutUs;
    },
  },
};
</script>


<style lang="scss" scoped>
.carousel__slide {
  display: block !important;
}
</style>