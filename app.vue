<template>
  <Header />
  <NuxtPage />
  <Footer />
</template>

<style lang="scss">
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
  color: white;
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
