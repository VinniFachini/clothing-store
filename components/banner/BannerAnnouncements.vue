<template>
  <div class="container banner-wrapper">
    <Announcement
      imageSrc="../../assets/images/free-shipping.png"
      title="Free Shipping"
      text="Free shipping in purchases above $347"
    />
    <Announcement
      imageSrc="../../assets/images/exchange.png"
      title="First Change Free"
      text="You have 30 days to change your mind!"
    />
    <Announcement
      imageSrc="../../assets/images/leather.png"
      title="Authentic Leather"
      text="Genuine leather with LWG quality certificate"
    />
    <Announcement
      imageSrc="../../assets/images/pix.png"
      title="10% off on Pix"
      text="Get 10% off by doing your payment via Pix"
    />
    <Announcement
      imageSrc="../../assets/images/credit-card.png"
      title="Credit Card"
      text="You can pay with any credit Card!"
    />
  </div>
</template>

<script>
import Announcement from "./Announcement.vue";
export default {
  components: { Announcement },
  setup() {},
};
</script>

<style lang="scss" scoped>
.banner-wrapper {
  display: flex;
  padding-block: 40px;
  align-items: center;
  justify-content: center;
  @media screen and (max-width: 1100px) {
    flex-wrap: wrap;
  }
}
</style>