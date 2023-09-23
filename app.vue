<template>
  <Header :categories="categoriesMenu" />
  <NuxtPage class="main" />
  <Footer />
</template>

<script>
export default {
  data() {
    return {
      categoriesMenu: []
    }
  },
  mounted() {
    this.fetchCategoriesMenu("./api.json")
  },
  methods: {
    fetchCategoriesMenu: async function (url) {
      const info = await fetch(url);
      const infoJson = await info.json();
      this.categoriesMenu = infoJson.categories;
    },
  }
}

</script>
<style lang="scss">
NuxtPage {
  padding-top: 119px;
}
input:-webkit-autofill,
input:-webkit-autofill:hover, 
input:-webkit-autofill:focus, 
input:-webkit-autofill:active{
    -webkit-box-shadow: 0 0 0 30px white inset !important;
}
html,
body {
  overflow-x: hidden;
}
a {
  text-decoration: none;
  color: #222;
}
.container {
  width: 100%;
  max-width: 1600px;
  margin: 0 auto;
  padding-inline: 20px;
  @media screen and (max-width: 1919px) {
    max-width: 1440px !important;
  }
  @media screen and (max-width: 1499px) {
    max-width: 1280px !important;
  }
  @media screen and (max-width: 1340px) {
    max-width: 1200px !important;
  }
}
</style>
